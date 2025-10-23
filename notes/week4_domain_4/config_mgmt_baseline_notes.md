# Configuration Management and Baseline Enforcement Notes

## Anchor
Configuration management ensures every network or server follows a secure, consistent template. 
Tools like Ansible, Puppet, and Terraform push configurations across environments. 
For example, Terraform can deploy VPCs, IAM roles, and security groups using versioned code. 
This standardization reduces drift and human error.

## Reverse
Automation mistakes can spread misconfigurations at scale. 
If a template disables encryption, every system might inherit that flaw. 
Always test infrastructure code in staging and review changes via Git before applying.
