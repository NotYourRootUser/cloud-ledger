| Feature            | **Internet Gateway (IGW)**                | **NAT Gateway (NAT GW)**                     |
| ------------------ | ----------------------------------------- | -------------------------------------------- |
| Purpose            | Connects VPC to Internet (public subnets) | Enables private subnets to reach Internet    |
| Traffic Direction  | Inbound + Outbound                        | Outbound only                                |
| IP Type Used       | Public / Elastic IPs                      | Private → translated to Elastic IP           |
| Placement          | Public Subnet                             | Public Subnet                                |
| Route Table Target | `igw-xxxx`                                | `nat-xxxx`                                   |
| Use Case           | Public web servers, ALBs                  | Private EC2 updates, outbound-only workloads |

- Private EC2 → NAT GW → IGW → Internet → back path reversed.