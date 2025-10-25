# VlAN vs Subnet Matrix
| Layer | Function | Scope | Example | Notes |
|--------|-----------|--------|----------|--------|
| VLAN | Broadcast isolation | Layer 2 | VLAN 10 (IoT), VLAN 20 (Guest) | Isolates frames at switch level |
| Subnet | IP addressing + routing boundary | Layer 3 | 192.168.10.0/24, 192.168.20.0/24 | Defines logical network per VLAN |
| Inter-VLAN Routing | Connects VLANs via router or L3 switch | Layer 3 | VLAN 10 ↔ VLAN 20 via router-on-a-stick | Enables communication between subnets |
| Trunk Link | Carries tagged frames for multiple VLANs | Layer 2 | Switch ↔ Router trunk | One cable, many VLANs (802.1Q) |

## Key concepts 
- **Broadcast scope ≠ routing scope.**
- VLANs isolate at Layer 2; Subnets seperate at layer 3 
- Tags keep traffic unique accros the table
- Native vlan mismatch = leak risk 
- tunk allowed list = traffic control
- ACLs refine what inter-VLAN traffic is allowed.