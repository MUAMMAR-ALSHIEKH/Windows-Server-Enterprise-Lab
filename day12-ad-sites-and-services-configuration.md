Day 12 – Active Directory Sites and Services Configuration

Overview

On Day 12, Active Directory Sites and Services were configured to simulate a structured enterprise network environment. This configuration helps organizations manage domain controllers across different network locations and control replication traffic efficiently.

A new Active Directory site named NEXORA-HQ was created to represent the company's headquarters. The appropriate subnet was then defined and associated with the site, allowing Active Directory to correctly identify which domain controllers belong to the network location.

The domain controller DC01 was moved from the default site to the newly created site to align with the simulated infrastructure design.

Objectives

Understand the purpose of Active Directory Sites and Services
Create a new Active Directory site for the organization
Define and assign network subnets to the site
Move the domain controller to the appropriate site
Review the replication topology within the site

Environment

Domain: nexora.local
Domain Controller: DC01
Site Name: NEXORA-HQ
Subnet: 192.168.10.0/24

Implementation Steps

Step 1 – Creating the Active Directory Site

Active Directory Sites and Services was opened from Server Manager.
A new site named NEXORA-HQ was created and linked to the default site link (DEFAULTIPSITELINK).

Step 2 – Creating the Network Subnet

A subnet representing the local network was created with the prefix 192.168.10.0/24.
This subnet was associated with the NEXORA-HQ site to ensure that domain controllers operating within this IP range are recognized as part of the headquarters location.

Step 3 – Moving the Domain Controller

The domain controller DC01 was initially located under the Default-First-Site-Name site.
It was moved to the NEXORA-HQ site to correctly reflect the infrastructure layout.

Step 4 – Reviewing Replication Settings

The NTDS Settings of DC01 were reviewed within the NEXORA-HQ site to verify the replication configuration and ensure that the directory service topology was correctly recognized.

Verification Results

The new Active Directory site was successfully created.
The subnet was correctly associated with the site.
The domain controller DC01 was moved to the NEXORA-HQ site.
Active Directory replication settings were accessible through NTDS Settings.

Screenshots Evidence

screenshots/day12/