<p align="center">
  <img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket Logo" width="250"/>
</p>

<h1 align="center">osTicket Help Desk Lab</h1>

<p align="center">
  Azure Deployment • Windows Administration • IIS • PHP • MySQL • Ticketing System
</p>

---

## 📌 Project Overview

In this project, I built and configured a functional **osTicket help desk environment from scratch** using a Windows virtual machine hosted in Microsoft Azure.

The lab included deploying the virtual infrastructure, configuring IIS and PHP, installing MySQL and HeidiSQL, setting Windows permissions, installing osTicket, and testing the completed ticketing system from both the end-user and technician perspectives.

This project provided hands-on experience with technologies and troubleshooting processes commonly used in **IT Help Desk and Technical Support environments**.

---

## 🎥 Video Demonstration

▶️ [Azure osTicket Help Desk Lab Demonstration](https://youtu.be/PwbPgSFsVe0)

---

## 🛠️ Technologies Used

| Technology | Purpose |
|---|---|
| **Microsoft Azure** | Hosted the Windows virtual machine |
| **Windows 10 Enterprise N 22H2** | Operating system for the help desk server |
| **Remote Desktop (RDP)** | Remote administration of the virtual machine |
| **Internet Information Services (IIS)** | Hosted the osTicket web application |
| **PHP 7.3.8** | Application runtime required by osTicket |
| **MySQL 5.5.62** | Database used by osTicket |
| **HeidiSQL** | Database administration and verification |
| **osTicket** | Help desk ticketing platform |

---

## 🎯 Lab Objectives

- Deploy a Windows virtual machine in Microsoft Azure
- Connect to and administer the VM using Remote Desktop
- Install and configure IIS
- Configure PHP for IIS
- Install and configure MySQL
- Install the osTicket application
- Configure Windows file permissions
- Connect osTicket to a MySQL database
- Access the osTicket administrator portal
- Submit a ticket through the end-user portal
- Verify successful ticket creation from the technician side

---

# ⚙️ Installation & Configuration

## 1. Create the Azure Resource Group

I created a Microsoft Azure Resource Group named **`osTicketing-system`** in the **East US 2** region to organize the resources used throughout the lab.

<p align="center">
  <img width="900" alt="Creating Azure Resource Group" src="https://github.com/user-attachments/assets/9f004952-7bcc-4783-9a84-bf5eb3967615" />
</p>

---

## 2. Create the Virtual Network

I created a virtual network named **`osTicketing-vnet`** and associated it with the `osTicketing-system` Resource Group.

<p align="center">
  <img width="900" alt="Creating Azure Virtual Network" src="https://github.com/user-attachments/assets/08776504-2d59-49f8-a821-8d799d3e2983" />
</p>

---

## 3. Deploy the Windows Virtual Machine

I deployed a virtual machine named **`osTicket-vm`** using:

- Windows 10 Enterprise N 22H2
- Standard_D4as_v7
- 4 vCPUs
- 16 GB RAM
- Local administrator account

<p align="center">
  <img width="900" alt="Creating osTicket Virtual Machine" src="https://github.com/user-attachments/assets/7744d928-e63d-4a92-baad-ac2259a80776" />
</p>

---

## 4. Connect to the VM with Remote Desktop

After deployment, I retrieved the VM's public IP address and connected to the Windows system using **Remote Desktop (RDP)**.

<p align="center">
  <img width="900" alt="Azure Virtual Machine Public IP" src="https://github.com/user-attachments/assets/121d2e43-44a6-4baf-afa4-b0f07649b8d3" />
</p>

<p align="center">
  <img width="900" alt="Remote Desktop Configuration" src="https://github.com/user-attachments/assets/30e1fecc-c75b-45b8-a911-ed75009f717a" />
</p>

<p align="center">
  <img width="900" alt="Connected Windows Virtual Machine" src="https://github.com/user-attachments/assets/ba445c00-2e28-4171-8da4-41bdb80a3964" />
</p>

---

## 5. Download the osTicket Installation Files

Inside the VM, I downloaded the required osTicket installation files and extracted the contents so they could be used during the server configuration.

<p align="center">
  <img width="900" alt="Downloading osTicket Files" src="https://github.com/user-attachments/assets/b501d499-a592-4549-b65a-aea5622d9a37" />
</p>

<p align="center">
  <img width="900" alt="Extracting osTicket Files" src="https://github.com/user-attachments/assets/74498e6d-9430-4168-abbe-f20f4540d96c" />
</p>

---

## 6. Install IIS and Enable CGI

I enabled **Internet Information Services (IIS)** through Windows Features.

Under:

`World Wide Web Services → Application Development Features`

I also enabled **CGI**, which is required for PHP to operate correctly with IIS.

<p align="center">
  <img width="900" alt="Enabling IIS" src="https://github.com/user-attachments/assets/71c22433-d7c7-489e-a63b-291273b2dfbc" />
</p>

<p align="center">
  <img width="900" alt="Enabling CGI" src="https://github.com/user-attachments/assets/9ff55681-26f6-43de-bad2-ee8fcbcd9d12" />
</p>

---

## 7. Install PHP Manager and URL Rewrite

I installed **PHP Manager for IIS** and the **IIS URL Rewrite Module** to prepare the web server for the osTicket application.

<p align="center">
  <img width="900" alt="Installing PHP Manager" src="https://github.com/user-attachments/assets/6fad8382-b20b-4d63-86d4-e9523bc9338a" />
</p>

<p align="center">
  <img width="900" alt="Installing URL Rewrite" src="https://github.com/user-attachments/assets/db57ee39-d01d-44fe-85c7-b141797a4a92" />
</p>

---

## 8. Install PHP

I created the following directory:

`C:\PHP`

I then extracted **PHP 7.3.8** into the directory so IIS could use PHP to run the osTicket application.

<p align="center">
  <img width="900" alt="Creating PHP Directory" src="https://github.com/user-attachments/assets/42f3f171-7d9c-4093-a635-9c24c9f302f4" />
</p>

<p align="center">
  <img width="900" alt="Extracting PHP Files" src="https://github.com/user-attachments/assets/86217770-3005-428a-bf4d-effea1408d71" />
</p>

---

## 9. Install MySQL and Visual C++ Redistributable

I installed **MySQL 5.5.62** using the Typical installation option and completed the Standard Configuration.

I also installed the required **Visual C++ Redistributable** package.

<p align="center">
  <img width="900" alt="Installing MySQL" src="https://github.com/user-attachments/assets/69719eda-edf5-469c-aaf5-648f23dc05e4" />
</p>

<p align="center">
  <img width="900" alt="Configuring MySQL" src="https://github.com/user-attachments/assets/b035485a-76b4-45ac-9f87-85d6a32b4c06" />
</p>

---

## 10. Register PHP with IIS

Using IIS Manager, I opened PHP Manager and registered:

`C:\PHP\php-cgi.exe`

I then restarted IIS so the configuration changes could take effect.

<p align="center">
  <img width="900" alt="PHP Manager IIS" src="https://github.com/user-attachments/assets/b08ae702-46da-48ad-ab41-4d33c717d609" />
</p>

<p align="center">
  <img width="900" alt="Registering PHP" src="https://github.com/user-attachments/assets/309cacb7-2ae7-403a-a56a-f103ada93223" />
</p>

---

## 11. Move osTicket Into the IIS Web Directory

I extracted **osTicket v1.15.8**, copied the `upload` folder into:

`C:\inetpub\wwwroot`

I then renamed the folder:

`osTicket`

<p align="center">
  <img width="900" alt="Extracting osTicket" src="https://github.com/user-attachments/assets/cd711a5f-f6c1-45c2-9c0f-ef1ae7080554" />
</p>

<p align="center">
  <img width="900" alt="Moving osTicket to IIS" src="https://github.com/user-attachments/assets/21e6484c-c2ad-42d9-b129-daf491e1c2c2" />
</p>

<p align="center">
  <img width="900" alt="osTicket IIS Directory" src="https://github.com/user-attachments/assets/bc8a87d5-8990-43fb-95f9-e945efd1b3c9" />
</p>

---

## 12. Enable Required PHP Extensions

After confirming that the osTicket site loaded through IIS, I enabled the required PHP extensions:

- `php_imap.dll`
- `php_intl.dll`
- `php_opcache.dll`

<p align="center">
  <img width="900" alt="osTicket IIS Website" src="https://github.com/user-attachments/assets/82edfdee-5e27-4da5-932f-a2a172eee34a" />
</p>

---

## 13. Configure the osTicket Configuration File

Inside:

`C:\inetpub\wwwroot\osTicket\include`

I renamed:

`ost-sampleconfig.php`

to:

`ost-config.php`

I then modified the Windows security settings so the installer could write to the configuration file.

<p align="center">
  <img width="650" alt="osTicket Configuration File" src="https://github.com/user-attachments/assets/814b05fb-d6ec-4c03-9716-25024a573514" />
</p>

<p align="center">
  <img width="900" alt="Windows File Permissions" src="https://github.com/user-attachments/assets/7f0e2e3b-846e-414e-8bb0-1d868e8c76ba" />
</p>

---

## 14. Configure File Permissions

I modified the permissions on `ost-config.php` to allow the installer to complete the configuration.

<p align="center">
  <img width="650" alt="Configuring osTicket File Permissions" src="https://github.com/user-attachments/assets/9f75d7ef-6dde-4b59-b15d-6e1e94e1dce1" />
</p>

<p align="center">
  <img width="650" alt="Assigning Windows Permissions" src="https://github.com/user-attachments/assets/c3ec5823-ea32-44ea-911e-0c2cea81ea8b" />
</p>

> **Security Note:** Broad permissions were used only for this isolated training environment. In a production environment, permissions should follow the principle of least privilege.

---

## 15. Configure the osTicket Installer

I returned to the browser and completed the initial osTicket configuration, including:

- Help desk information
- Administrator account
- Email settings
- Database connection information

<p align="center">
  <img width="900" alt="osTicket Installer" src="https://github.com/user-attachments/assets/dac65046-8d8b-4f64-9a0e-549268021417" />
</p>

<p align="center">
  <img width="900" alt="osTicket Configuration" src="https://github.com/user-attachments/assets/06471f2e-7f38-48aa-90c9-b887ea683a8d" />
</p>

<p align="center">
  <img width="900" alt="osTicket Database Configuration" src="https://github.com/user-attachments/assets/cdca7440-5722-4df4-b1c9-b2630d29afe1" />
</p>

---

## 16. Install and Configure HeidiSQL

I installed **HeidiSQL** and created a connection to the MySQL server so I could manage and verify the osTicket database.

<p align="center">
  <img width="900" alt="HeidiSQL Configuration" src="https://github.com/user-attachments/assets/26a4a423-a652-4d3e-80d4-bebcf5e51e9b" />
</p>

> **Lab Note:** Simple database credentials were used only inside this isolated training environment. Strong, unique credentials should always be used in production systems.

---

## 17. Verify Successful Installation

The osTicket installation completed successfully.

At this point, the environment provided access to both:

- **End-User Support Portal**
- **Staff Control Panel**

<p align="center">
  <img width="900" alt="Successful osTicket Installation" src="https://github.com/user-attachments/assets/65f455d1-039c-40cb-95fa-4c03817f955f" />
</p>

---

## 18. Verify the Database and Admin Portal

Using HeidiSQL, I confirmed that osTicket successfully created the necessary database tables.

I then accessed the osTicket Staff Control Panel and verified that the administrator account could successfully log in.

<p align="center">
  <img width="900" alt="osTicket Database Tables" src="https://github.com/user-attachments/assets/686d05d0-3901-4c20-8b5c-e3df458e7b99" />
</p>

<p align="center">
  <img width="900" alt="osTicket Admin Login" src="https://github.com/user-attachments/assets/69a51060-9691-43d4-b6621b416647" />
</p>

---

# 🎫 Ticket Testing

## 19. Create an End-User Support Ticket

To test the completed environment, I opened the osTicket end-user portal and created a simulated support request for a user experiencing an internet connectivity issue.

<p align="center">
  <img width="900" alt="osTicket End User Portal" src="https://github.com/user-attachments/assets/de66a64f-6882-4b86-b69d-366a10741e2d" />
</p>

<p align="center">
  <img width="900" alt="Creating Test Support Ticket" src="https://github.com/user-attachments/assets/231067d7-06f1-4fa1-9f91-431c48f7c7a9" />
</p>

<p align="center">
  <img width="900" alt="Submitting osTicket Support Request" src="https://github.com/user-attachments/assets/80c053ae-e473-4522-b6b1-7b40c418393c" />
</p>

---

## 20. Verify the Ticket From the Technician Portal

After submitting the support request, I returned to the Staff Control Panel.

The newly created ticket successfully appeared in the technician queue, confirming that the end-user portal, database, and administrative ticketing interface were functioning correctly.

<p align="center">
  <img width="900" alt="Ticket Appearing in osTicket Queue" src="https://github.com/user-attachments/assets/2e2e18c9-7173-4e94-bb58-9003ea849ca5" />
</p>

<p align="center">
  <img width="900" alt="Verified osTicket Support Ticket" src="https://github.com/user-attachments/assets/6d1af1f3-22d6-4864-8a60-b4f06b1b33aa" />
</p>

---

# 🧠 Skills Demonstrated

This project provided hands-on experience with:

- Microsoft Azure Virtual Machine Deployment
- Windows 10 Administration
- Remote Desktop Protocol (RDP)
- IIS Web Server Configuration
- PHP Installation and Configuration
- MySQL Database Installation
- HeidiSQL Database Administration
- Windows NTFS File Permissions
- Web Application Deployment
- osTicket Installation and Configuration
- Help Desk Ticketing Systems
- End-User Support Workflows
- Troubleshooting and Configuration Verification
- Technical Documentation

---

# ✅ Project Outcome

I successfully built a functional **osTicket help desk environment from the ground up** using Microsoft Azure and Windows.

The completed system allowed an end user to submit a support ticket and an administrator or technician to receive and manage that ticket through the Staff Control Panel.

This lab strengthened my understanding of **help desk operations, Windows administration, ticketing systems, permissions, databases, web services, and technical troubleshooting**—skills directly applicable to entry-level **IT Support, Help Desk, and Service Desk roles**.

---

## 🔗 Connect With Me

**GitHub:** [Jerron-it](https://github.com/Jerron-it)

**LinkedIn:** [Add LinkedIn Profile Here](YOUR-LINKEDIN-URL)
