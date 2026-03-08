# Day 3 – Additional Domain Controller (DC02)

## 🎯 Objective
The objective of Day 3 was to enhance *Active Directory availability and redundancy* by adding a second domain controller to the existing domain.

---

## 🖥️ Environment
- Domain Name: nexora.local
- Primary DC: DC01
- Additional DC: DC02
- Operating System: Windows Server
- Platform: VMware Workstation

---

## 🔧 Tasks Performed

### 1. DC02 Server Preparation
- Created a new Windows Server virtual machine
- Renamed the server to DC02
- Configured a static IPv4 address
- Verified network connectivity to DC01

---

### 2. Domain Join
- Joined DC02 to the existing nexora.local domain
- Restarted the server to apply domain membership
- Verified domain login using domain administrator credentials

---

### 3. AD DS Installation
- Installed *Active Directory Domain Services (AD DS)* role on DC02
- Initiated domain controller promotion

---

### 4. Domain Controller Promotion
- Selected *Add a domain controller to an existing domain*
- Enabled:
  - DNS Server role
  - Global Catalog (GC)
- Configured DSRM password
- Completed prerequisite checks successfully
- Installed and rebooted the server automatically

---

## ✅ Validation & Verification
- Confirmed domain login screen displays NEXORA\Administrator
- Verified AD management tools are available
- Confirmed both DC01 and DC02 appear under the *Domain Controllers* OU
- Verified replication health using: 
repadmin /replsummary

---

## 📸 Evidence
Screenshots for Day 3 are available in:
Screenshots/day3/
---

## 🏁 Conclusion
DC02 was successfully promoted as an *Additional Domain Controller*, providing redundancy and improved availability for Active Directory and DNS services within the Nexora enterprise environment.
