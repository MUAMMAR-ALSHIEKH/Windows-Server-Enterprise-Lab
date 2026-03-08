Day 13 – Windows Server Update Services (WSUS) Deployment

Overview

On Day 13, Windows Server Update Services (WSUS) was deployed to centralize update management within the domain environment. WSUS allows administrators to control how Microsoft updates are distributed to servers and client machines, reducing bandwidth usage and improving update management across the organization.

The WSUS role was installed on the domain server and configured to synchronize updates directly from Microsoft Update. During the configuration process, update languages, supported Microsoft products, and update classifications were selected. After completing the configuration wizard, the initial synchronization process was started to download available updates.

Objectives

Deploy the Windows Server Update Services role
Configure WSUS to synchronize updates from Microsoft Update
Select update languages and supported products
Define update classifications for synchronization
Perform the initial synchronization process

Environment

Domain: nexora.local
Server: DC01
Role Installed: Windows Server Update Services (WSUS)

Implementation Steps

Step 1 – Installing the WSUS Role

The Windows Server Update Services role was installed through the Add Roles and Features wizard in Server Manager. Required role services including WSUS Services and Windows Internal Database were selected during the installation process.

Step 2 – Configuring Update Storage

A local directory was specified to store downloaded updates. This directory allows WSUS to locally store update files that will later be distributed to domain clients.

Step 3 – Opening the WSUS Management Console

After the installation was completed, the WSUS console was opened from the Tools section in Server Manager to begin the configuration process.

Step 4 – Running the WSUS Configuration Wizard

The configuration wizard was used to define how the server retrieves updates. The server was configured to synchronize updates directly from Microsoft Update without using a proxy server.

Step 5 – Selecting Languages, Products, and Classifications

English was selected as the update language. Relevant Microsoft products such as Windows Server and Windows operating systems were chosen to ensure only necessary updates are synchronized. Update classifications including Critical Updates, Security Updates, Definition Updates, and general Updates were also selected.

Step 6 – Starting the Initial Synchronization

After completing the configuration wizard, the initial synchronization process was started. This allows the WSUS server to connect to Microsoft Update and begin downloading metadata for available updates.

Verification Results

The WSUS role was successfully installed on the server.
The WSUS console was accessible and fully configured.
Synchronization with Microsoft Update was successfully initiated.
The server began retrieving update information for the selected products and classifications.

Screenshots Evidence

screenshots/day13/