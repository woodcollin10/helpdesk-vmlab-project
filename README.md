# Help Desk Virtual Lab Project

## Overview

This project documents the creation of a virtualized IT help desk environment using VirtualBox, Windows Server 2022, and Windows 11 virtual machines.

The goal of this lab is to simulate a small organizational IT environment while developing hands-on experience with:
- Active Directory
- Windows administration
- Networking
- Domain management
- Help desk troubleshooting
- Ticket sytem creation
- Ticket resolution workflows
- User account management
- Remote desktop support

This repository will continue to expand with additional help desk scenarios, troubleshooting exercises, ticketing workflows, and system administration tasks.

---

# 1. Active Directory Management
This phase of the project focused on organizing Active Directory to simulate a real-world enterprise environment. Organizational Units (OUs), users, security groups, and workstation objects were structured to support future onboarding, offboarding, access management, and help desk workflows.

Tom Assigned to Sales Department
- Tom was moved into the Sales Organizational Unit to align with departmental user management practices and role-based administration.

<img width="1254" height="879" alt="Tom in Sales" src="https://github.com/user-attachments/assets/7e8b8725-cd57-442b-9e3c-a9033f953696" />

Bob Assigned to Human Resources
- Bob was moved into the Human Resources Organizational Unit to simulate departmental user organization within Active Directory.

<img width="1258" height="883" alt="Bob in HR" src="https://github.com/user-attachments/assets/1a779507-305f-41d7-a139-1006c29e05c3" />

IT Administration Structure
- A dedicated IT Organizational Unit was created to manage administrative accounts and future help desk operations. This structure supports role separation and centralized administration.

<img width="1263" height="886" alt="IT in domain" src="https://github.com/user-attachments/assets/fe1e50c1-cce2-48ee-b220-97c98594993e" />

Workstation Organization
- Domain-joined workstations were moved into a dedicated Workstations Organizational Unit to improve organization and prepare for future Group Policy management.

<img width="1259" height="883" alt="Workstations in Domain" src="https://github.com/user-attachments/assets/f0bd351d-7de3-4dcf-ae8b-7a8f4a7ba7d5" />

Skills Demonstrated:
- Active Directory Administration
- Organizational Unit (OU) Management
- User Account Administration
- Security Group Management
- Domain Management
- Identity and Access Management (IAM)
- Workstation Organization
- Enterprise Directory Structure Design

---
# 2. osTicket Deployment Lab

## Overview

This project focused on deploying and configuring osTicket, an open-source help desk ticketing system, within a Windows Server 2022 lab environment. The deployment required configuring IIS, PHP, MySQL, URL Rewrite, FastCGI, file permissions, and database connectivity to create a functional ticket management platform.

The objective was to simulate a real-world help desk deployment while developing practical experience with web server administration, application deployment, troubleshooting, and service configuration.

---

## Technologies Used

- Windows Server 2022
- Internet Information Services (IIS)
- PHP 8.2
- MySQL 8.0
- osTicket v1.17.7
- URL Rewrite Module 2.1
- FastCGI
- PowerShell
- Oracle VirtualBox

---

## Project Objectives

- Deploy a web-based help desk application
- Configure IIS to support PHP applications
- Install and configure MySQL database services
- Configure URL Rewrite and FastCGI
- Manage file permissions for web applications
- Troubleshoot web server and database errors
- Verify successful application deployment

---

## Deployment Process

The deployment consisted of:

1. Installing MySQL Server
2. Installing PHP and required extensions
3. Installing IIS URL Rewrite Module
4. Configuring FastCGI within IIS
5. Creating PHP Handler Mappings
6. Deploying osTicket files to IIS web root
7. Configuring required PHP modules
8. Creating and securing the osTicket configuration file
9. Connecting osTicket to the MySQL database
10. Completing the osTicket installation wizard
11. Verifying portal and administrative access

---

## Troubleshooting Performed

During deployment, several issues were identified and resolved:

### URL Rewrite Errors

- Resolved HTTP 500.19 configuration errors
- Resolved HTTP 500.52 URL Rewrite errors
- Verified rewrite rules and web.config configuration

### PHP Configuration

- Installed missing PHP MySQLi extension
- Configured PHP FastCGI integration
- Validated PHP execution within IIS

### File Permissions

- Created ost-config.php from sample configuration
- Granted temporary write permissions
- Removed elevated permissions after installation

### Database Connectivity

- Verified MySQL service operation
- Configured database credentials
- Resolved MySQL authentication issues

---

## Skills Demonstrated

### Windows Server Administration

- IIS Management
- Service Configuration
- File System Permissions
- PowerShell Administration

### Web Application Deployment

- PHP Configuration
- FastCGI Configuration
- URL Rewrite Configuration
- Application Installation

### Database Administration

- MySQL Installation
- Database Configuration
- User Authentication
- Connectivity Troubleshooting

### Troubleshooting

- Log Analysis
- Error Identification
- Root Cause Analysis
- Service Validation

---

## Results

Successfully deployed a fully functional osTicket help desk platform capable of:

- Accepting support tickets
- Managing administrative users
- Hosting a customer support portal
- Providing a staff management interface
- Storing ticket information within a MySQL database

---

<img width="1670" height="1020" alt="osTicket Confirmation" src="https://github.com/user-attachments/assets/9f30338b-d182-4ae0-a779-b17e08346d4f" />





<img width="1675" height="1015" alt="osTicket Page" src="https://github.com/user-attachments/assets/9a7223a1-4193-4723-ab57-6b2c91938400" />

---

## Key Takeaways

This project provided hands-on experience deploying a production-style web application within a Windows Server environment. It strengthened skills in IIS administration, PHP configuration, MySQL management, troubleshooting complex application errors, and integrating multiple technologies to deliver a working business application.

---

## 3. Internal DNS and IIS Host Header Configuration

### Overview

After successfully deploying osTicket, the next objective was to improve accessibility by replacing the default application path (`http://localhost/osTicket`) with a user-friendly internal URL.

To accomplish this, an internal DNS record was created within the Active Directory environment and IIS was configured with a dedicated website and host header binding. This allowed users to access the help desk platform using a simple, memorable address.

Final URL:

```text
http://helpdesk.woodtech.com
```

---

### Objectives

- Create an internal DNS record for the help desk platform
- Configure IIS host header bindings
- Create a dedicated IIS website for osTicket
- Eliminate the need for `/osTicket` in the URL
- Simulate a real-world enterprise application deployment

---

### Technologies Used

- Windows Server 2022
- Active Directory DNS
- Internet Information Services (IIS)
- osTicket v1.17.7

---

### Implementation Details

#### DNS Configuration

A new **Host (A) record** was created within the `woodtech.com` forward lookup zone.

| Record Name | IP Address |
|-------------|------------|
| `helpdesk` | `192.168.10.10` |

This allowed domain-joined machines to resolve:

```text
helpdesk.woodtech.com
```

to the osTicket server.

#### IIS Configuration

A dedicated IIS website named **HelpDesk** was created with the following settings:

| Setting | Value |
|----------|-------|
| Site Name | `HelpDesk` |
| Physical Path | `C:\inetpub\wwwroot\osTicket` |
| Type | `http` |
| Port | `80` |
| Host Name | `helpdesk.woodtech.com` |

The existing osTicket application was removed from the **Default Web Site** after successful testing.

---

### Validation

The configuration was verified by accessing the following URLs from a client workstation:

```text
http://helpdesk.woodtech.com
```

```text
http://helpdesk.woodtech.com/scp
```

Successful access confirmed:

- Proper DNS resolution
- Correct IIS host header configuration
- Functional osTicket deployment
- Client-to-server connectivity

---

### Skills Demonstrated

- DNS administration
- IIS website configuration
- Host header bindings
- Internal web application deployment
- Active Directory integration
- Network troubleshooting

---

### Screenshots

#### DNS Host Record

<img width="1684" height="1018" alt="ServerDNS" src="https://github.com/user-attachments/assets/3b07c884-b872-4445-a0f5-ab0a82a6a09e" />

*Created an internal DNS record to resolve `helpdesk.woodtech.com` to the osTicket server.*

#### IIS Website Configuration and Validation

<img width="1684" height="1018" alt="ServerDNS" src="https://github.com/user-attachments/assets/560fcd7d-e058-42c0-ad1b-7d88f8fb73c0" />

*Configured a dedicated IIS website named **HelpDesk** with a host header binding for `helpdesk.woodtech.com` and verified successful access to the osTicket Support Center from a client workstation.*

---

### Outcome

By implementing internal DNS and IIS host header bindings, the osTicket deployment now mirrors a production-style enterprise environment. Users can access the help desk platform through a simplified URL without requiring knowledge of server names, IP addresses, or application paths.

---
