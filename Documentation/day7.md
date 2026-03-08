Day 7 – File Server Deployment (FS01)

Objective

Deploy and configure a secure enterprise file server within the Nexora domain environment to provide controlled departmental access using NTFS and Share permissions based on security groups.

Environment

Server Name: FS01
Domain: nexora.local
Server Role: File Server
Infrastructure: On-Premises Virtual Lab

Role Installation

The File Server role was installed using Server Manager.
Post-installation validation confirmed:

. Successful role deployment

. Server properly joined to the domain

. Network connectivity verified


Folder Structure Design

A structured departmental directory was created on a dedicated data volume:

D:\
- Shares
- IT
- HR
- Finance
- Sales

This structure ensures logical separation of departmental data while maintaining centralized management.

Security Group Strategy

Access control was implemented using Role-Based Access Control (RBAC).
Permissions were assigned to domain security groups instead of individual users.

Security Groups Used:

. IT_Users

. HR_Users

. Finance_Users

. Sales_Users


NTFS Permission Configuration

For each department folder:

. Corresponding security group assigned Modify permission

. SYSTEM retained Full Control

. Domain Admins retained Full Control

. Direct user-level permissions avoided

. Unnecessary inherited permissions removed where applicable


This enforces the Principle of Least Privilege and maintains centralized control.

Share Permission Configuration

The root directory D:\Shares was shared as:

Share Name: Departments

Share Permissions:

. Authenticated Users: Read

. Domain Admins: Full Control


Access enforcement is primarily controlled through NTFS permissions to maintain granular security.

Validation and Testing

Testing was performed using domain-joined client machines.

Validation Steps:

. Logged in as IT domain user

. Confirmed access to IT folder

. Verified denial of access to HR, Finance, and Sales folders

. Tested file creation and modification within allowed directory

. Confirmed consistent behavior across client systems


Security Principles Applied

. Role-Based Access Control

. Least Privilege Access Model

. Group-Based Permission Assignment

. Centralized Domain Authentication

. Structured Enterprise File Architecture


Evidence

Screenshots stored under:

screenshots/day7/


Outcome

A fully functional and secure departmental file server was successfully deployed and validated.
The configuration aligns with enterprise standards and demonstrates proper implementation of NTFS and Share permission models within a domain environment.

Day: 7
Status: Completed