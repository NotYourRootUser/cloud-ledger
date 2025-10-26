## Key Points

- Security Groups are **instance-level** firewalls. They are **stateful**, meaning once traffic is allowed in, the response is automatically allowed back out.  
- Network ACLs are **subnet-level** filters. They are **stateless**, meaning inbound and outbound rules are checked separately.  
- **Evaluation order:**  
  `Internet → NACL → SG → EC2`  
- NACL rules are processed in **number order** and can **allow or deny**.  
- SGs only contain **allow** rules and deny everything else implicitly.  
- **Default behavior:**  
  - SG → allow all outbound, deny all inbound  
  - NACL → allow all inbound and outbound  
- Together, SG and NACL form **defense in depth**:  
  NACL = fence at the subnet boundary  
  SG = guard at the instance door  

---

## Flow Scenarios

**Inbound Web Request:**  
`User → Internet → NACL → SG → EC2`  
NACL filters traffic first at the subnet; SG checks it next at the instance.

**Return Traffic:**  
`EC2 → SG → NACL → Internet`  
SG remembers the session; NACL re-checks outbound because it’s stateless.

**Blocked SSH Attempt:**  
NACL rule denies port 22.  
SG never sees the attempt because it’s stopped at the subnet edge.

---

## Notes

- SG = micro control per instance  
- NACL = macro control per subnet  
- Both are needed for layered security  
- Voice seeding helped internalize *how* packets move, not just the definitions

**Summary:**  
> NACL checks first, SG checks second.  
> Stateless perimeter first, stateful instance last.  
> Fence then guard, macro to micro.
