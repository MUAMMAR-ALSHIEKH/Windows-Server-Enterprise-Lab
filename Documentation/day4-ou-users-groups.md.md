# Day 4 – Organizational Units, Users, and Groups Management

## Overview
Day 4 focused on building a realistic and scalable *Active Directory logical structure* for the Nexora enterprise environment.  
This included designing Organizational Units (OUs), creating security groups, managing users, and automating bulk user creation using PowerShell.

---

## Objectives
- Design an enterprise-ready OU structure
- Create departmental security groups
- Create and manage domain users
- Automate bulk user creation
- Apply Active Directory best practices

---

## Domain Information
- Domain Name: nexora.local
- Forest Functional Level: Windows Server
- Environment Type: Enterprise Active Directory Lab

---

## Organizational Unit (OU) Design

The following OU structure was created under the domain:

nexora.local 
└── NEXORA 
├── IT
├── HR 
├── Finance
├── Sales 
├── Servers 
└── Workstations

---

### Design Notes

- Department-based OUs allow easier management and policy application
- Servers and Workstations are separated for security and control
- Domain Controllers remain in the default *Domain Controllers* OU as per Microsoft best practices

---

## Security Groups Configuration

Security groups were created to support *role-based access control*.

### Groups Created

*IT Department*
- IT-Admins
- IT-Users

*HR Department*
- HR-Users

*Finance Department*
- Finance-Users

*Sales Department*
- Sales-Users

### Group Configuration
- Group Scope: Global
- Group Type: Security

These groups will later be used for:
- File and folder permissions
- Group Policy assignment
- Administrative delegation

---

## User Account Management

### Manual User Creation
- Domain users were manually created inside their respective OUs
- Standard naming conventions were followed
- Accounts were enabled and verified

---

## Automated Bulk User Creation

To simulate a real enterprise environment, *120 domain users* were created using a PowerShell script.

### Automation Details
- Total Users Created: 120
- Users distributed across:
  - IT
  - HR
  - Finance
  - Sales
- Temporary password assigned to all users.
- Security setting enabled:
- User must change password at next logon

### Benefits
- Demonstrates automation skills
- Reduces administrative overhead
- Reflects real-world enterprise practices

---

## Group Membership Assignment

- Users were added to their respective departmental security groups
- Access control is managed via groups rather than individual users
- This approach improves security and simplifies management

---

## Validation and Testing

The following checks were successfully completed:
- Verified OU structure and hierarchy
- Confirmed user placement in correct OUs
- Verified security group membership
- Tested domain user login
- Confirmed forced password change at first login

---

## Screenshots and Evidence

All screenshots related to Day 4 tasks are stored in:
screenshots/day4/

---

### Screenshot Coverage
- OU creation
- Security group creation
- Manual user creation
- Bulk user creation (PowerShell)
- Group membership verification
- User login testing

---

## Day 4 Completion Status

- Organizational Units created and structured.
- Security groups configured.
- Users created manually and via automation.
- Best practices applied.
- Environment prepared for Group Policy implementation.