<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Setup From Scratch</h1>
This tutorial outlines the process of setting up and configuring the open-source help desk ticketing system osTicket from scratch, including installation, initial configuration, and preparing the system for ticket management.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How to create, work, and resolves tickets within osTicket](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure – Hosted the virtual machine
- Windows 10 Enterprise N 22H2 – Operating system used for the osTicket server
- Internet Information Services (IIS) – Web server used to run osTicket
- PHP – Required to run the osTicket application
- MySQL – Database used to store ticket and user information
- HeidiSQL – Used to manage the MySQL database
- osTicket – Open-source help desk ticketing system
- Remote Desktop (RDP) – Used to connect to and configure the virtual machine

<h2>Operating Systems Used </h2>

- Windows 10 Enterprise N 22H2</b> (21H2)

<h2>osTicket Setup Stages</h2>

- Create the Virtual Machine
- Connect to the VM
- Install IIS
- Install PHP
- Install MySQL
- Download and Install osTicket
- Create the Database
- Finish the osTicket Setup

<h2>osTicket Installation & Configuration</h2>

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
  
<img width="1440" height="900" alt="RD Add Comp" src="https://github.com/user-attachments/assets/30e1fecc-c75b-45b8-a911-ed75009f717a" />

<img width="1440" height="900" alt="Screenshot 2026-08-17 at 4 38 32 PM" src="https://github.com/user-attachments/assets/ba445c00-2e28-4171-8da4-41bdb80a3964" />
</p>
<p>
Connecting to the Virtual Machine – I am locating the virtual machine’s public IP address in Azure, entering that IP into the Windows App, and connecting to the VM. Once connected, I am logging in with the osUser account I created earlier.
</p>
<br />

<p>
<img width="1440" height="900" alt="Download os" src="https://github.com/user-attachments/assets/b501d499-a592-4549-b65a-aea5622d9a37" />
<img width="1440" height="900" alt="Extract All to desk" src="https://github.com/user-attachments/assets/74498e6d-9430-4168-abbe-f20f4540d96c" />


</p>
<p>
Downloading and Extracting osTicket Files – I am using Microsoft Edge to download the osTicket installation ZIP file. Once the download is complete, I will open the Downloads folder, right-click the file, select Extract All, and extract the installation files so I can use them for the setup.
</p>
<br />

<p>
<img width="1440" height="900" alt="Screenshot 2026-08-17 at 9 13 07 PM" src="https://github.com/user-attachments/assets/71c22433-d7c7-489e-a63b-291273b2dfbc" />
  <img width="1440" height="900" alt="Screenshot 2026-08-17 at 9 16 53 PM" src="https://github.com/user-attachments/assets/9ff55681-26f6-43de-bad2-ee8fcbcd9d12" />
</p>
<p>
Enabling IIS and CGI – I am opening Windows Features, enabling Internet Information Services (IIS), then expanding World Wide Web Services → Application Development Features and checking CGI so osTicket can run properly on the web server.
</p>
<br />

<p>
<img width="1440" height="900" alt="Screenshot 2026-08-17 at 9 20 57 PM" src="https://github.com/user-attachments/assets/6fad8382-b20b-4d63-86d4-e9523bc9338a" />
<img width="1440" height="900" alt="Screenshot 2026-08-17 at 9 24 13 PM" src="https://github.com/user-attachments/assets/db57ee39-d01d-44fe-85c7-b141797a4a92" />
</p>
<p>
Installing PHP Manager and URL Rewrite Module – I am opening the osTicket installation files on the desktop and installing both PHP Manager for IIS and the IIS URL Rewrite Module to prepare the web server for osTicket.
</p>
<br />

<p>
<img width="1440" height="900" alt="Screenshot 2026-08-17 at 10 24 48 PM" src="https://github.com/user-attachments/assets/42f3f171-7d9c-4093-a635-9c24c9f302f4" />
<img width="1440" height="900" alt="Screenshot 2026-08-17 at 10 25 27 PM" src="https://github.com/user-attachments/assets/86217770-3005-428a-bf4d-effea1408d71" />
</p>
<p>
Creating the PHP Folder and Extracting PHP – I am creating a new folder named PHP on the C: drive. Then I will go back to the osTicket installation files, right-click PHP 7.3.8, select Extract All, and extract the files into the new C:\PHP folder.
</p>
<br />

<p>
<img width="1440" height="900" alt="Screenshot 2026-08-17 at 10 41 46 PM" src="https://github.com/user-attachments/assets/69719eda-edf5-469c-aaf5-648f23dc05e4" />
<img width="1440" height="900" alt="Screenshot 2026-08-17 at 10 42 23 PM" src="https://github.com/user-attachments/assets/b035485a-76b4-45ac-9f87-85d6a32b4c06" />
</p>
<p>
Installing MySQL and VC++ Redistributable – I am going back to the osTicket installation files and installing MySQL 5.5.62 using the Typical setup. For the configuration, I am selecting Standard Configuration, and once MySQL is set up, I will install VC_redist.x86.
</p>
<br />

<p>
<img width="1440" height="900" alt="Screenshot 2026-08-17 at 10 47 34 PM" src="https://github.com/user-attachments/assets/b08ae702-46da-48ad-ab41-4d33c717d609" />
<img width="1440" height="900" alt="Screenshot 2026-08-17 at 10 48 25 PM" src="https://github.com/user-attachments/assets/309cacb7-2ae7-403a-a56a-f103ada93223" />
</p>
<p>
Registering PHP in IIS – I am searching for IIS Manager and running it as an administrator. Then I will open PHP Manager, register PHP by selecting C:\PHP\php-cgi.exe, and restart IIS so the changes can take effect.
</p>
<br />

<p>
<img width="1440" height="900" alt="Screenshot 2026-08-17 at 10 55 24 PM" src="https://github.com/user-attachments/assets/cd711a5f-f6c1-45c2-9c0f-ef1ae7080554" />
<img width="1440" height="900" alt="Screenshot 2026-08-17 at 10 57 04 PM" src="https://github.com/user-attachments/assets/21e6484c-c2ad-42d9-b129-daf491e1c2c2" />
<img width="1440" height="900" alt="Screenshot 2026-08-17 at 11 09 32 PM" src="https://github.com/user-attachments/assets/bc8a87d5-8990-43fb-95f9-e945efd1b3c9" />
</p>
<p>
Moving osTicket Files to IIS – I am extracting osTicket-v1.15.8.zip, copying the upload folder into C:\inetpub\wwwroot, and then renaming the folder to osTicket.
</p>
<br />


<p>
<img width="1440" height="900" alt="Screenshot 2026-08-18 at 9 51 44 AM" src="https://github.com/user-attachments/assets/82edfdee-5e27-4da5-932f-a2a172eee34a" />
</p>
<p>
Opening the osTicket Site and Enabling PHP Extensions – I am going to *Sites → Default Web Site → Browse :80 (http) to open the site. Then I will go back to PHP Manager and enable php_imap.dll, php_intl.dll, and php_opcache.dll.
</p>
<br />

<p>
<img width="671" height="588" alt="Screenshot 2026-08-19 at 8 36 48 PM" src="https://github.com/user-attachments/assets/814b05fb-d6ec-4c03-9716-25024a573514" />
<img width="1440" height="900" alt="Screenshot 2026-08-18 at 10 05 24 AM" src="https://github.com/user-attachments/assets/7f0e2e3b-846e-414e-8bb0-1d868e8c76ba" />
</p>
<p>
Renaming and Securing the osTicket Configuration File – I am going to C:\inetpub\wwwroot\osTicket\include, renaming ost-sampleconfig.php to ost-config.php, then opening Properties → Security → Advanced and disabling inheritance so I can change the file permissions.
</p>
<br />

<p>
<img width="624" height="690" alt="Screenshot 2026-08-19 at 8 40 57 PM" src="https://github.com/user-attachments/assets/9f75d7ef-6dde-4b59-b15d-6e1e94e1dce1" />
</p>
<p>
Assigning Permissions to the Configuration File – I am selecting Add → Select a Principal, typing Everyone, and clicking Check Names so I can assign the needed permissions to the ost-config.php file.
</p>
<br />

<p>
<img width="567" height="702" alt="Screenshot 2026-08-19 at 8 42 21 PM" src="https://github.com/user-attachments/assets/c3ec5823-ea32-44ea-911e-0c2cea81ea8b" />
</p>
<p>
Completing the osTicket Setup – I am going back to the web browser to continue the osTicket setup, filling in the required information, and making sure the admin email and system email are different before continuing.
</p>
<br />
<p>
<img width="1440" height="900" alt="Screenshot 2026-08-18 at 10 36 01 AM" src="https://github.com/user-attachments/assets/dac65046-8d8b-4f64-9a0e-549268021417" />
<img width="1440" height="900" alt="Screenshot 2026-08-18 at 10 37 46 AM" src="https://github.com/user-attachments/assets/06471f2e-7f38-48aa-90c9-b887ea683a8d" />
<img width="1440" height="900" alt="Screenshot 2026-08-18 at 10 45 25 AM" src="https://github.com/user-attachments/assets/cdca7440-5722-4df4-b1c9-b2630d29afe1" /> 
</p>
<p>
Installing and Connecting HeidiSQL – Before finishing the osTicket setup, I am installing HeidiSQL from the osTicket files on the desktop. Once it is installed, I will open HeidiSQL, create a new session, enter root as both the username and password (For this lab enviorment only), and open the connection to the osTicketing System.
</p>
<br />
<p>
<img width="1440" height="900" alt="Screenshot 2026-08-18 at 10 47 42 AM" src="https://github.com/user-attachments/assets/26a4a423-a652-4d3e-80d4-bebcf5e51e9b" />
</p>
<p>
Confirming Successful osTicket Installation – The osTicket installation has completed successfully. I can now see the confirmation page, along with the links for the osTicket user portal and the Staff Control Panel, which shows that the system is ready for final configuration and testing.
</p>
<br />
<p>
<img width="1440" height="900" alt="Screenshot 2026-08-18 at 10 48 44 AM" src="https://github.com/user-attachments/assets/65f455d1-039c-40cb-95fa-4c03817f955f" />
<img width="1440" height="900" alt="Screenshot 2026-08-18 at 10 54 17 AM" src="https://github.com/user-attachments/assets/686d05d0-3901-4c20-8b5c-e3df458e7b99" />
<img width="1440" height="900" alt="Screenshot 2026-08-18 at 10 55 54 AM" src="https://github.com/user-attachments/assets/69a51060-9691-43d4-bc42-b6621b416647" />
</p>
<p>
Verifying the Database and Logging Into osTicket – Now that osTicket is installed, I am refreshing the osTicket database in HeidiSQL to confirm the tables were created. Then I will open http://localhost/osTicket/scp/login.php in the web browser and log in using the adminuser account I created earlier to confirm the admin portal is working.
</p>
<br />
<p>
<img width="1440" height="900" alt="Screenshot 2026-08-18 at 10 58 03 AM" src="https://github.com/user-attachments/assets/de66a64f-6882-4b86-b69d-366a10741e2d" />
<img width="1440" height="900" alt="Screenshot 2026-08-18 at 10 59 58 AM" src="https://github.com/user-attachments/assets/231067d7-06f1-4fa1-9f91-431c48f7c7a9" />
<img width="1440" height="900" alt="Screenshot 2026-08-18 at 11 01 25 AM" src="https://github.com/user-attachments/assets/80c053ae-e473-4522-b6b1-7b40c418393c" />
</p>
<p>
Opening the End-User Portal and Creating a Test Ticket – I am going to http://localhost/osTicket/ to open the end-user portal. Once the page loads, I will create a new test ticket using Jane Doe and a simulated no-internet issue, then submit it so I can verify that it appears on the admin side.
</p>
<br />
<p>
<img width="1440" height="900" alt="Screenshot 2026-08-18 at 11 01 42 AM" src="https://github.com/user-attachments/assets/2e2e18c9-7173-4e94-bb58-9003ea849ca5" />
<img width="1440" height="900" alt="Screenshot 2026-08-18 at 11 01 54 AM" src="https://github.com/user-attachments/assets/6d1af1f3-22d6-4864-8a60-b4f06b1b33aa" />  
</p>
<p>
Verifying the Test Ticket – After submitting the test ticket, I am switching back to the admin portal and refreshing the page. The new ticket appears successfully, confirming that osTicket is installed, configured, and working properly from the end-user side to the admin side.
</p>
<br />




