## Project Goals

The goal of this project is to design and implement a complete Windows Server enterprise lab environment that simulates a real-world corporate infrastructure.

The lab focuses on building a centralized identity and resource management system using Active Directory, while deploying essential enterprise services such as DNS, DHCP, file services, update management, and backup solutions.

Through this project, practical system administration skills were developed including domain management, network services configuration, security policy enforcement, and enterprise infrastructure documentation.

## Network Design

The lab environment is built on a private network using the 192.168.10.0/24 subnet.

Core infrastructure servers are assigned static IP addresses to ensure consistent network communication and service reliability, while client machines receive IP addresses dynamically via DHCP.

DNS is integrated with Active Directory to provide centralized name resolution, and replication is configured between domain controllers to ensure high availability and directory redundancy.

Network Structure:
- Network Range: 192.168.10.0/24
- DHCP Range: 192.168.10.21 – 192.168.10.200
- Static IP allocation for core infrastructure servers

## Servers Overview

The lab environment consists of multiple Windows Server systems, each responsible for specific infrastructure services.

DC01
Primary Domain Controller responsible for Active Directory Domain Services, DNS, DHCP, WSUS, and FSMO role ownership.

DC02
Secondary Domain Controller providing redundancy for directory services and DNS replication to ensure high availability.

FS01
Dedicated file server hosting departmental shared folders for HR, IT, Sales, and Finance with controlled access through NTFS permissions and security groups.

WS01
A domain-joined client machine used to validate domain authentication, Group Policy application, DHCP functionality, and software update deployment.

## Lessons Learned

This project provided hands-on experience in designing and managing a Windows Server enterprise infrastructure.

Key lessons learned include:
- Planning and implementing an Active Directory domain structure
- Deploying redundant domain controllers for high availability
- Managing users, groups, and Organizational Units
- Applying centralized security policies through Group Policy
- Implementing core network services such as DNS and DHCP
- Managing file services and access control using NTFS permissions
- Configuring Windows Server Update Services (WSUS) for centralized update management
- Performing system state backups for disaster recovery scenarios

The lab strengthened practical system administration skills and improved understanding of enterprise IT infrastructure management.
