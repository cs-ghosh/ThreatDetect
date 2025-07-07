## Ping Connectivity Tests

### Static IP Configuration

This step validates how IP addressing and routing affect host-to-host connectivity. 

---


| Test Case                    | Windows IP        | Kali IP           | Expected Result | Actual Result |
|-----------------------------|-------------------|-------------------|------------------|----------------|
| Same Subnet                 | 192.168.0.113     | 192.168.0.112     | Ping success  | Ping success|
| Different Subnet (No Route) | 192.168.50.10     | 192.168.100.10    | Ping fail     | Ping fail   |
| Proper Route Added          | 192.168.50.10     | 192.168.50.20     | Ping success  | Ping success  |

---

### Observation:

- **Same Subnet:**  
  With both machines on 192.168.0.0/24, ping worked successfully. Packets were directly delivered without needing a router.

- **Different Subnet (No Route):**  
  When Kali was on 192.168.100.0/24 and Windows on 192.168.50.0/24, ping failed. The system showed "Network is Unreachable"

- **Proper Route Added:**  
  After configuring Kali with an IP in the same subnet as Windows (192.168.50.0/24) and defining the correct gateway (192.168.50.1), ping succeeded. 
---
