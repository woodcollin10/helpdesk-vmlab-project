# Help Desk Virtual Lab Project

## Overview

This project documents the creation of a virtualized IT help desk environment using VirtualBox, Windows Server 2022, and Windows 11 virtual machines.

The goal of this lab is to simulate a small organizational IT environment while developing hands-on experience with:
- Active Directory
- Windows administration
- Networking
- Domain management
- Help desk troubleshooting
- Ticket resolution workflows
- User account management
- Remote desktop support

This repository will continue to expand with additional help desk scenarios, troubleshooting exercises, ticketing workflows, and system administration tasks.

---

# Active Directory Management
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
# osTicket Deployment Lab

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



---

## Key Takeaways

This project provided hands-on experience deploying a production-style web application within a Windows Server environment. It strengthened skills in IIS administration, PHP configuration, MySQL management, troubleshooting complex application errors, and integrating multiple technologies to deliver a working business application.
