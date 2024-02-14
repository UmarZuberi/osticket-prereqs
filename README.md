<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Azure Virtual Machine
- IIS Protocal (Internet Information Service)
- PHP Manager
- Rewrite Module
- VC Redist
- MySQL
- Heidi SQL
- osTicket
- All neccesary files https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6

<h2>Installation Steps</h2>

1. Begin by navigating to https://portal.azure.com/ to initiate the creation of a virtual machine. Configure the virtual machine with Windows 10 Pro, specifically version 22H2. Ensure that the virtual machine is equipped with a minimum of 2 vCPUs and 16 GB of memory.

2. After successfully creating the virtual machine, establish a connection to it using the public IP address assigned to the VM. Utilize the Remote Desktop Connection application for this connection process.

![image](https://github.com/UmarZuberi/osticket-prereqs/assets/159849539/38bd0fb5-e158-4e4d-a811-a884e1095b37)
![image](https://github.com/UmarZuberi/osticket-prereqs/assets/159849539/225a0e22-c8a1-4632-a00c-a4ad35f476a5)

3. Upon establishing a connection to your virtual machine, navigate to the Control Panel. Within the Control Panel, locate and open the "Programs" section. From there, select "Turn Windows features on and off."

![image](https://github.com/UmarZuberi/osticket-prereqs/assets/159849539/a252a280-38f8-42f0-a581-da71d8165a2c)

![image](https://github.com/UmarZuberi/osticket-prereqs/assets/159849539/51e79344-7b67-4f69-ad0b-d46df5a54839)

4. To enable IIS in Windows with CGI and Common HTTP Features, follow these steps:
   
Navigate to "World Wide Web Services" in the "Application Development Features" section.
Check the boxes for "CGI" and "Common HTTP Features" under "World Wide Web Services."

![image](https://github.com/UmarZuberi/osticket-prereqs/assets/159849539/7951285a-6688-4aae-8eba-23d726516fe5)

![image](https://github.com/UmarZuberi/osticket-prereqs/assets/159849539/199ab235-647d-44c6-8886-579b001812a4)

   














