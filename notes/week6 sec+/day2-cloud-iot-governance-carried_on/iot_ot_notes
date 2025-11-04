# Mantrap and Visitor Logs Notes

Mantraps are two-door security systems that allow only one person to enter at a time. They prevent tailgating and unauthorized access to secure areas. The system enforces a sequence where the first door must close and lock before the second door opens.  

Visitor logs document every guest entering the facility. Each record should include the visitor's name, the host, the purpose of the visit, time in, time out, and identification method used. Logs support audits and investigations by providing evidence of who entered and when.  

Common weaknesses include manual override keys, broken sensors, or paper-only logs that can be lost or altered. Digital logs with access control are preferred.  

Mantrap checks should verify that:
- Both doors never open simultaneously.
- Override use is logged and reviewed.
- Alarm and sequence logs are regularly inspected.

Visitor log checks should confirm:
- All entries have required fields.
- Logs are protected from tampering.
- Retention period matches audit requirements.


# IoT Segmentation Notes

IoT segmentation isolates connected devices such as cameras, sensors, and meters into dedicated network segments to limit exposure. Each IoT subnet operates with least privilege, allowing communication only to its management systems or data collectors.  

Network Access Control (NAC) and certificate-based authentication identify and validate devices before they join the network. Segmentation prevents lateral movement from an IoT device into administrative or production environments.  

Key configuration checks:
- Each IoT VLAN has firewall rules blocking access to core networks.
- Devices use unique credentials and valid certificates.
- Management traffic uses encrypted channels.
- Monitoring detects devices that cross VLAN boundaries.

Testing should include:
- Ping or traceroute from IoT to admin VLAN (should fail).
- Review ACLs for deny statements on internal destinations.
- Verify certificate rotation schedules and revoke expired certs.


# OT Safety Roles Notes

Operational Technology (OT) systems manage industrial control equipment such as PLCs, SCADA controllers, and plant sensors. Safety depends on clearly defined human roles.  

Typical roles include:
- Plant Operator: runs the system day to day but does not modify configurations.
- OT Security Engineer: maintains and secures the control network.
- Control Systems Owner: authorizes major changes and reviews incidents.
- Incident Response Lead: coordinates containment and recovery during faults or attacks.

These roles prevent unsafe actions such as live patching or remote rebooting during production.  

Good practice:
- Maintain a RACI matrix showing who is Responsible, Accountable, Consulted, and Informed.
- Require change approvals for firmware updates or configuration edits.
- Use a documented escalation path when a PLC malfunctions: isolate, notify, restore from backup.
- Keep training current and restrict shared credentials.

Auditing should confirm roles exist, escalation procedures are tested, and unsafe maintenance actions are prohibited.
