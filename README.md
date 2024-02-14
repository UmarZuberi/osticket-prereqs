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

- Create Azure Virtual Machine with Windows OS 
- Connect to VM via Remote Desktop Connection.
- Enable IIS and install PHP Manager in Control Panel.
- Install Rewrite Module and VC Redist within IIS.
- Download MySQL installer, install MySQL Server, and Heidi SQL.
- Download osTicket and follow installation instructions.
- Configure each component and test functionality.
- Implement security measures (firewalls, permissions, SSL).
- https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6 <-- all necessary downloads




<h2>Installation Steps</h2>

1. Begin by navigating to https://portal.azure.com/ to initiate the creation of a virtual machine. Configure the virtual machine with Windows 10 Pro, specifically version 22H2. 2vCPU is recomended.

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


NOTE: Ensure all Common HTTP Features are checked during IIS installation.

To verify IIS installation/enabled:

A. Open a browser and search for "127.0.0.1".
B. Confirm the browser displays a default IIS landing page indicating successful installation/enabling.

![image](https://github.com/UmarZuberi/osticket-prereqs/assets/159849539/9a30c7d2-07b4-41a9-9a81-131e2c5cb367)

5. Download and install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi) from the Installation Files. Follow the installation wizard and complete the installation process.

6. Download and install the Rewrite Module (rewrite_amd64_en-US.msi) from the Installation Files.

7. Create a folder named "PHP" in the C drive (C:\PHP).

8. Download PHP 7.3.8 (php-7.3.88-nts-Win32-VC15-x866.zip) from the Installation Files. Unzip the contents into the C:\PHP folder.

*Note: If prompted, choose to "Keep" the file when the attention message appears.

![image](https://github.com/UmarZuberi/osticket-prereqs/assets/159849539/9c637b47-1838-4ecb-a531-3011928cb20a)

![image](https://github.com/UmarZuberi/osticket-prereqs/assets/159849539/fdfd6972-0a6c-4189-b06e-2534a437e77d)

9. Download VC_redist.x86.exe from the installation files and install it. Follow the setup wizard to complete the installation process.

10. Download and install MySQL 5.5.62 (mysql-5.5.62-win32.msi). Follow these steps in the setup wizard: Choose Typical Setup
    -> Launch Configuration Wizard (after install)
    -> Select Standard Configuration
    -> Set the new root password as: Password1 (don't do this for real world scenario)

    ![image](https://github.com/UmarZuberi/osticket-prereqs/assets/159849539/bc55f1cc-c539-4812-bd85-cd45dd5f6251)

     -> click execute

    ![image](https://github.com/UmarZuberi/osticket-prereqs/assets/159849539/929ff4f2-b7ff-497c-b379-d26efb07e2fe)

11. Search for "IIS" in the Windows search bar and open it as an administrator. The program should appear similar to this.

    ![image](https://github.com/UmarZuberi/osticket-prereqs/assets/159849539/f46adad3-5088-458b-8c4b-8dee7ee8551a)

12. Within IIS, proceed to register PHP by clicking on "PHP Manager."

    ![image](https://github.com/UmarZuberi/osticket-prereqs/assets/159849539/7a41d8c8-8ae1-4c4e-b46c-ee225166cb39)

--> register PHP

![image](https://github.com/UmarZuberi/osticket-prereqs/assets/159849539/db879b72-f1e5-4535-a674-5c24fa0ece9e)


--> You'll need to provide a path to the PHP executable file (php-cgi.exe). Navigate to the following location:

Go to C Drive -> PHP -> Click on the "php-cgi" file.

![image](https://github.com/UmarZuberi/osticket-prereqs/assets/159849539/ac8ee311-be60-4646-b0bb-efb5f013316d)

--> click restart

![image](https://github.com/UmarZuberi/osticket-prereqs/assets/159849539/1e25130a-f65b-43b6-bee8-e1777283e773)


13. Install osTicket v1.15.8:

  --> Download osTicket from the Installation Files Folder.
    
  --> Extract the downloaded file and copy the "upload" folder to "C:\inetpub\wwwroot".
  
  --> Rename the copied "upload" folder to "osTicket" within "C:\inetpub\wwwroot".
  
  --> Reload IIS again.

  
14. In IIS:
    
  --> Go to "Sites" -> "Default" -> "osTicket".
  
  --> On the right, click "Browse *:80" to access osTicket.

  ![image](https://github.com/UmarZuberi/osticket-prereqs/assets/159849539/d52657c0-bc82-433b-80e8-89b6bbbbabbc)

 --> don't wprry about unchecked section

 ![image](https://github.com/UmarZuberi/osticket-prereqs/assets/159849539/ff423955-10e7-4b08-8425-26f3d9cf7cd7)

 
To enable the extensions in osTicket:

--> Go back to IIS: Navigate to "Sites" -> "Default" -> "osTicket".

--> Double-click on PHP Manager.

--> Click on "Enable or disable an extension".

![image](https://github.com/UmarZuberi/osticket-prereqs/assets/159849539/731623e1-1c44-4130-b942-ddb255238e3e)

![image](https://github.com/UmarZuberi/osticket-prereqs/assets/159849539/002419b6-d692-4d45-ab37-4e84cee905ae)


To enable the required extensions in osTicket:

A. In PHP Manager, navigate to "Enable or disable an extension".
B. Check the boxes for the following extensions:

--> php_imap.dll

--> php_intl.dll

--> php_opcache.dll

Make sure to save the changes after enabling each extension.

![image](https://github.com/UmarZuberi/osticket-prereqs/assets/159849539/971f6068-a1e3-4cc6-8119-d87064e9a706)


15. To rename the file in the osTicket folder and set permissions:
    
A. Navigate to File Explorer and search for "C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php".

B. Rename "ost-sampleconfig.php" to "ost-config.php".

C. Right-click on the renamed file and go to "Properties".

D. Click on "Security", then "Advanced", and disable inheritance by selecting "Remove all inherited permissions from this object".

E. Click "Add" to add new permissions.


















    






   














