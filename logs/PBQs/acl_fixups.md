### **Common Rule Patterns**

Speak and visualize these:

| Rule Pattern | Example | Meaning |
| --- | --- | --- |
| **Permit All Outbound** | `permit ip any any eq 80` | Allow all web traffic |
| **Permit Specific Host** | `permit tcp host 10.0.0.5 any eq 22` | Allow one host to SSH |
| **Deny Subnet** | `deny ip 10.0.0.0 0.0.0.255 any` | Block local subnet |
| **Permit Internal → External** | `permit ip 10.0.1.0 0.0.0.255 any` | Allow inside network to go out |
| **Deny All** | `deny ip any any` | Implicitly ends the list |

Key anchor line to repeat:

> “ACLs stop reading after the first match.”
> 

---

### **3 Scenario 

**ACL A:**

```
deny tcp any any eq 80
permit tcp 10.0.0.0 0.0.0.255 any eq 80

permit tcp 10.0.0.0 0.0.0.255 any eq 80
deny tcp any any eq 80

```

- Problem: web traffic from 10.0.0.0/24 is still blocked.

**Fix:** move the **permit** above the **deny** (first-match logic).

**ACL B:**

```
permit tcp any any eq 22
permit tcp any any eq 80
permit udp any any eq 53

```

- Problem: everything else is blocked even for DNS.

**Fix:** add a **final permit** for outbound DNS:

`permit udp any any eq 53`
