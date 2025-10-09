# Cloud Service Model Security Matrix

When you move from on-prem to the cloud, control slowly shifts from the customer to the provider.  
The shared responsibility model defines who protects what at each level.

---

### On-Prem
You handle everything yourself – hardware, network, OS, apps, and data.  
Full control, but full responsibility.

### IaaS
The provider takes care of the physical hardware and virtualization layer.  
You’re still responsible for the OS, updates, software, and all data inside your VMs.

### PaaS
The provider also manages the operating system and runtime.  
You just deploy your code and protect your data and access.

### SaaS
The provider runs the full stack — app, OS, and infrastructure.  
You only manage user accounts, permissions, and how data is used or shared.

---

**Quick rules**
- More convenience = less control.  
- Provider secures *the cloud*; customer secures *what’s in the cloud*.  
- Most cloud breaches come from customer misconfigurations, not provider failure.

**Examples:**  
- IaaS → AWS EC2, Azure VM  
- PaaS → AWS Lambda, Azure App Service  
- SaaS → Google Drive, Salesforce
