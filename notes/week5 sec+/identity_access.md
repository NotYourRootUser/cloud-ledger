# Identity and Access preload Anchor \

## Anchoring info 
- Goal: map governance bullets into cloud controls so access is precise and reversible.
- Least privilege: role per task, policies scoped to exact resources, use Conditions and principal tags to limit blast radius.
- Distribution and attestation: use Access Advisor and Access Analyzer to see last used and potential resource findings. schedule regular attestations and tie them to tickets.
- Exception process: require JIT elevation only, short session durations, approval ticket attached to creds, and automatic expiry.
- Revocation SOP: immediate console disable, inactivate and delete access keys, remove group membership, detach policies, rotate secrets, record actions in an offboard log.
- Version control: keep all IAM, SCP and policy artifacts in Terraform or CloudFormation. PRs are the change record.

## Reverse challenges (questions and trouble spots)
- What if attestations become checkbox theater and nobody actually reviews entries?
- What if temporary elevation is requested but the approver forgets to set an expiry, or tickets stack up?
- What if policies are edited directly in the console and never land in Git?
- What if offboarding revokes console access but leaves API keys or service principals active?
- What if SCPs are applied too broadly and break legitimate automation?
- How do we prove an offboard actually removed every privilege across accounts and services?
- What happens when a contractor needs quick access at 02:00 and the JIT pipeline is slow?

## eXploit (practical controls, commands, snippets, runbook bits)
- CI guardrail for wildcards
  - run terraform plan, output JSON, fail PR if any policy statement contains Action of "*" or Resource of "*" for IAM, S3, KMS.
  - example check:
    - terraform plan -out=tfplan.binary
    - terraform show -json tfplan.binary > tfplan.json
    - parse tfplan.json and fail on wildcard actions

- Least privilege sample policy pattern
  - allow only s3:GetObject and s3:ListBucket on a specific bucket
  - deny destructive actions unless principal has a tag like role=admin

- SCP pattern idea
  - apply an SCP that denies iam:* and s3:* by default to child accounts and allow exceptions via explicit OU policy
  - keep SCPs narrow and test in a sandbox OU first

- Just in time elevation
  - use Identity Center roles with 1 hour sessions or
  - assume-role via STS with duration-seconds set to 3600 and require an approval ticket id in the session name or tags

- Offboarding quick CLI steps (order matters)
  1. delete or disable login profile for the user
  2. list and inactivate then delete access keys
  3. remove user from groups and detach policies
  4. remove SSO assignments or revoke federated sessions where possible
  5. rotate Secrets Manager secrets tagged to the user and rotate any CI/CD tokens they could access
  6. append a JSON log to offboard-logs/<user>-YYYYMMDD.json and commit it

- CloudTrail and evidence collection
  - query CloudTrail for CreateAccessKey, DeleteAccessKey, ConsoleLogin for the subject
  - keep the cloudtrail outputs and the offboard log together in the incident ticket

- Offboard automation pipeline sketch
  - HR triggers webhook to Step Function
  - Step Function runs Lambdas to perform IAM actions, rotate secrets, and produce a final artifact
  - failure to complete within 15 minutes escalates to security ops

- Practical checklist to enforce now
  - PRs failing on policy wildcards for sensitive services
  - weekly IAM Access Analyzer report turned into attestation tickets for roles unused for 90 days
  - monthly secrets owner review via tags
  - offboard webhook must return success code and an artifact to close the HR ticket

## 5 quick scenarios and the concise fix
1. wildcard s3:* found in a policy
   - fix: replace with exact actions, apply SCP deny on wildcard until PR fixes it
2. contractor leaving but email kept for a week
   - fix: immediate key purge, disable console, rotate secrets they had access to
3. app created policy in console outside IaC
   - fix: detect drift, import policy to repo, require authored policy file then remove console policy
4. finance role unused for 90 days
   - fix: disable role, open attestation ticket to re-enable with justification
5. admin role exists in every account
   - fix: apply SCPs to restrict admin actions, force admin access through a central jump role with MFA and session approval

## Final note
- treat policies as code, treat offboarding as automation, and treat attestations as a safety culture not a checkbox. keep the evidence chain in Git and CloudTrail so the story is always verifiable.
