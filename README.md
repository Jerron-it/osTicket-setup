<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Setup From Scratch</h1>
This tutorial outlines the process of setting up and configuring the open-source help desk ticketing system osTicket from scratch, including installation, initial configuration, and preparing the system for ticket management.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How to create, work, and resolves tickets within osTicket](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure – Hosted the virtual machine
- Windows 10 – Operating system used for the osTicket server
- Internet Information Services (IIS) – Web server used to run osTicket
- PHP – Required to run the osTicket application
- MySQL – Database used to store ticket and user information
- HeidiSQL – Used to manage the MySQL database
- osTicket – Open-source help desk ticketing system
- Remote Desktop (RDP) – Used to connect to and configure the virtual machine

<h2>Operating Systems Used </h2>

- Windows 10 Pro</b> (21H2)

<h2>osTicket Setup Stages</h2>

- Create the Virtual Machine
- Connect to the VM
- Install IIS
- Install PHP
- Install MySQL
- Download and Install osTicket
- Create the Database
- Finish the osTicket Setup

<h2>osTicket Setup Stages</h2>

<p>
<img width="1440" height="900" alt="ResourceGroup" src="https://github.com/user-attachments/assets/9f004952-7bcc-4783-9a84-bf5eb3967615" />

</p>
<p>
Creating the Resource Group – I am creating a new Resource Group named osTicketing-system and setting the region to East US 2. Once I review the information, I will click Create.
</p>
<br />

<p>
<img width="1440" height="900" alt="vnet" src="https://github.com/user-attachments/assets/08776504-2d59-49f8-a821-8d799d3e2983" />

</p>
<p>
Creating the Virtual Network – Next, I am creating a virtual network named osTicketing-vnet and attaching it to the osTicketing-system Resource Group. I am also keeping the region set to East US 2 before clicking Create.
</p>
<br />

<p>
<img width="1440" height="900" alt="VirtualMachine" src="https://github.com/user-attachments/assets/7744d928-e63d-4a92-baad-ac2259a80776" />
  
</p>
<p>
Creating the Virtual Machine – After creating the Resource Group and Virtual Network, I am creating a new virtual machine named osTicket-vm. I am using Windows 10 Enterprise N, version 22H2 with a Standard_D4as_v7 size, which gives the VM 4 vCPUs and 16 GB of memory. I am also creating the administrator account and using osUser as the username.
</p>
<br />

<p>
<img width="1440" height="900" alt="VMip" src="https://github.com/user-attachments/assets/121d2e43-44a6-4baf-afa4-b0f07649b8d3" />
<img width="1440" height="900" alt="VMip" src="https://github.com/user-attachments/assets/967cd95d-08ad-4767-85e6-0e4e996caf1d" />
<img width="1440" height="900" alt="Screenshot 2026-08-17 at 4 38 32 PM" src="https://github.com/user-attachments/assets/ba445c00-2e28-4171-8da4-41bdb80a3964" />
</p>
<p>
Connecting to the Virtual Machine – I am locating the virtual machine’s public IP address in Azure, entering that IP into the Windows App, and connecting to the VM. Once connected, I am logging in with the osUser account I created earlier.
</p>
<br />
