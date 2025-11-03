# BYOD → MDM / MAM → Geofencing (ARX)

## Anchor
- BYOD: Bring Your Own Device — personal devices used for corporate access.
- MDM: full-device management (OS-level enforcement, device wipe).
- MAM: app-level management (containerization, selective wipe).
- Geofence: access control based on location/network (trusted IPs / VPN).

## Reverse Questions
- If a device is outside trusted IPs and not MAM-compliant → restrict access, require step-up auth, log session.
- If an MDM-enrolled device is lost → full wipe; if only MAM, selective wipe corporate container.

## Diagram

Diagram: BYOD → MDM / MAM → Conditional Access flow.

![BYOD Geofence Flow](byod_geofence_flow.png)
*Figure: BYOD device path; MDM vs MAM split; Conditional Access checks device posture + network geofence; outcomes: Full vs Limited Access. Saved as `byod_geofence_flow.png`.*


## Quick policy example 
Policy: FinanceCorp-Geofence
Condition:
  - Source IP ∈ {203.0.113.0/24, 198.51.100.0/24} OR device connected via Company-VPN
Controls:
  - If condition TRUE: Allow full access to corporate email, trading app, file shares.
  - If condition FALSE: Require MFA + device compliance (MDM enrolled OR MAM container) AND restrict to view-only for sensitive documents.
  - If device non-compliant: Deny access to sensitive endpoints; allow limited, auditable read-only access to low-risk resources.
