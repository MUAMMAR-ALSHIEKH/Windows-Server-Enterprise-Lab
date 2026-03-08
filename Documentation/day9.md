# Day 6 – DHCP Server Configuration & Troubleshooting

## Overview
In Day 6, a DHCP Server was deployed and configured in the Active Directory environment to dynamically assign IP addresses to domain and non-domain clients.  
This day also included real-world troubleshooting of a critical networking issue related to APIPA addressing in a virtualized environment.

---

## Environment Details
- *Domain Name:* NEXORA.local  
- *DHCP Server:* DC01 (Windows Server)  
- *Clients:* Windows Client Virtual Machines  
- *Virtualization Platform:* VMware  
- *Network Range:* 192.168.10.0/24  

---

## Objectives
- Install and configure the DHCP Server role
- Create and activate an IPv4 DHCP scope
- Configure essential DHCP options
- Verify dynamic IP assignment to clients
- Troubleshoot APIPA (169.254.x.x) addressing issues
- Document findings and resolution

---

## DHCP Server Installation
- Installed the *DHCP Server* role on DC01
- Completed post-installation configuration
- Authorized the DHCP server in Active Directory

---

## DHCP Scope Configuration
- Created an IPv4 Scope with the following details:
  - *Network ID:* 192.168.10.0/24
  - *IP Range:* 192.168.10.20 – 192.168.10.100
  - *State:* Active
- Scope status verified as healthy (green)

---

## DHCP Options Configuration
Configured the following scope options:
- *Option 003 – Router:* Default gateway IP
- *Option 006 – DNS Server:* DC01 IP address
- *Option 015 – DNS Domain Name:* nexora.local
- *WINS Servers:* Not configured (not required)

---

## Client Configuration
- Clients configured to:
  - Obtain IP address automatically
  - Obtain DNS server automatically
- Both domain-joined and non-domain clients tested

---

## Issue Encountered: APIPA Address Assignment

### Problem Description
- Client machines were receiving *APIPA addresses (169.254.x.x)*
- DHCP console showed active leases (e.g., 192.168.10.21)
- Clients failed to receive the assigned IP
- Issue persisted even when clients were removed from the domain
- Errors appeared during ipconfig /renew

---

## Root Cause Analysis
- VMware built-in *DHCP Service* was enabled
- Conflict occurred between:
  - VMware DHCP
  - Windows Server DHCP (DC01)
- This caused a DHCP race condition where DHCP offers failed to reach clients correctly

---

## Resolution
- Disabled *VMware DHCP Service* on the host machine
- Ensured only *one DHCP server* existed in the broadcast domain
- Renewed client IP configuration

```cmd
ipconfig /release
ipconfig /renew

Results
Clients successfully obtained valid IP addresses from DC01
APIPA issue fully resolved
Network connectivity restored
DNS resolution and Group Policy updates functioned correctly
Verification
The following commands were used to verify proper functionality:

ipconfig /all
ping 192.168.10.10
nslookup nexora.local
gpupdate /force

All tests completed successfully without errors.
Key Takeaways
Only one DHCP server should exist per broadcast domain
Virtualization platforms can introduce hidden DHCP conflicts
APIPA addresses usually indicate network-level issues, not domain or GPO problems
Systematic troubleshooting is essential in enterprise environments
Status

✅ Day 6 completed successfully