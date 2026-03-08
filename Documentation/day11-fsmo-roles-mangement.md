Day 11 – FSMO Roles Management

Overview

On Day 11, the focus was on understanding and validating the Flexible Single Master Operations (FSMO) roles within the Active Directory environment.

FSMO roles are specialized domain controller tasks that ensure consistency and prevent conflicts in multi-domain controller environments. Each role is assigned to a specific domain controller to handle critical directory operations.

In this lab, the current FSMO role holders were identified and verified using both command-line tools and graphical management consoles.

Objectives

Understand the purpose of FSMO roles in Active Directory
Identify which domain controller holds each FSMO role
Verify domain-level and forest-level roles
Document the FSMO configuration within the environment

Environment

Domain: nexora.local
Domain Controllers: DC01, DC02
Verification Tools: PowerShell, Active Directory Management Consoles

Implementation Steps

Step 1 – Verifying FSMO Roles via Command Line

The FSMO role holders were identified using the following command:

netdom query fsmo

This command lists all five FSMO roles and the domain controller currently holding them.

Step 2 – Verifying Domain-Level FSMO Roles

The domain-level FSMO roles were verified using Active Directory Users and Computers.

The following roles were reviewed:

RID Master
PDC Emulator
Infrastructure Master

Each role assignment was confirmed through the Operations Masters interface.

Step 3 – Verifying Forest-Level FSMO Roles

Forest-level FSMO roles were verified using Active Directory Domains and Trusts and the Active Directory Schema console.

The following roles were validated:

Domain Naming Master
Schema Master

These roles ensure proper management of domain naming operations and directory schema modifications across the forest.

Validation

All FSMO roles were successfully identified and verified within the Nexora Active Directory environment.

The environment currently maintains stable FSMO role assignments, ensuring proper directory operations and management functionality.

Screenshots Evidence

screenshots/day11/