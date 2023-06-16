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

- Remote Desktop Connection to Virtual Machine
- Install/Enable Internet Information Services (IIS) in Windows
- Install Web Platform Installer
- Download/Install osTicket v1.15.8
- Download/Install HeidiSQL
- Create Database for osTicket in HeidiSQL

<h2>Installation Steps</h2>

<p>
Go to Azure and create a Virtual Machine
</p>
<br />

<p>
Click "Create New" under the Resource group name and name it "RG-osTicket". Fill out the rest of the settings as done in the pictures below.
</p>
<br />

<p>
Connect to the Virtual Machine using Remote Desktop by copying and pasting the VM's public IP address into the Remote Desktop Connection window.
  
  Note: Search on your local machine "Remote Desktop Connection" to find the Window
</p>
<br />

<p>
In the virtual machine, we will begin by installing the Web Platform Installer. Search for "Control Panel" and select "Uninstall a Program" under Programs.

</p>
<br />

<p>
Enable Internet Information Services (IIS) by selecting "Turn Windows features on or off" in the Control Panel and enabling IIS from the available services. Also make sure to select CGI and Common HTTP Features.

</p>
<br />

<p>
Download and install PHP Manager for IIS.
</p>  
Link: https://drive.google.com/file/d/1RHsNd4eWIOwaNpj3JW4vzzmzNUH86wY_/view
</p>
<br />

<p>
Download and install the Rewrite Module.
</p>
Link: https://drive.google.com/file/d/1tIK9GZBKj1JyUP87eewxgdNqn9pZmVmY/view
</p>
<br />

<p>
Create the directory C:\PHP.
</p>
<br />

<p>
Download PHP 7.3.8 and unzip the contents into C:\PHP.
</p>
Link: https://drive.google.com/file/d/1snNMtLdCOpMtkCyD4mvl9yOOmvVIp9fP/view
</p>
<br />

<p>
Download and install VC_redist.x86.exe.
</p>
Link: https://drive.google.com/file/d/1s1OsGF3-ioO0_9LYizPRiVuIkb3lFJgH/view
</p>
<br />

<p>
Download and install MySQL5.5.62.
</p>
Link: https://drive.google.com/file/d/1_OWh9p7VQLcrB0q_V7qT8yHl0xo5gv7z/view
</p>
<br />
  
  
<p>
Launch MySQL to configure and set up credentials. 
</p>
<br />

<p>
Click Start, search for IIS and right click the application to run as administrator.
</p>
<br />

<p>
Click on PHP Manager, then "Register new PHP version" and select "php-cgi" in the C:\PHP folder we created earlier.
</p>
<br />

<p>
Click on the name of your server and restart it now.
</p>
<br />

<p>
Download osTicket v1.15.8.
</p>
Link: https://drive.google.com/file/d/1VeVXKlzHDRjeaVUL99ptq7qYbrbXdFxJ/view?usp=drive_link
</p>
<br />

<p>
Extract and copy "upload" folder in osTicket into C:\inetpub\wwwroot. Rename it "osTicket" after.
</p>
<br />

<p>
Go back to IIS and restart the server again.
<br />

<p>
Now in IIS, go to sites -> default -> osTicket. On the right side, click "Browse *80"
</p>
<br />

<p>
You should now see the osTicket installer page through the browser window that opens. Review the recommendations/prerequisites.
</p>
<br />

<p>
Go back to IIS -> Default -> osTicket, select PHP Manager and enable the required PHP extensions (php_imap.dll, php_intl.dll, php_opcache.dll) for osTicket.
</p>
<br />

<p>
Refresh the osTicket site in the browser to see the changes after enabling the PHP extensions.
</p>
<br />

<p>
Rename "ost-sampleconfig.php" to "ost-config.php" in the directory "C:\inetpub\wwwroot\osTicket\include\".
</p>
<br />

<p>
Change the permissions of "ost-config.php" by right-clicking on it, selecting "Properties", navigating to the "Security" tab, clicking on the "Advanced" button, disabling inheritance, removing all inherited permissions, adding new permissions for everyone, and giving full control.
</p>
<br />

<p>
Continue with the osTicket installer in the browser window and fill in the required details on the form up to the Database Settings. Write them down so you do not forget for later!
</p>
<br />

<p>
Download and install HeidiSQL using the provided defaults. This will allow us to connect to the mySQL server and set up a database for osTicket to use. 
</p>
Link: https://docs.google.com/document/d/1WovrX2DaS9xkfaSr4LXyB4YnnWpXIgPCMMbbfgHmGVw/edit?usp=drive_link
</p>
<br />

<p>
Open HeidiSQL and create a new session with the username and password you used when setting up the MySQL server. Connect to the session by selecting "Open".
</p>
<br />

<p>
Create a database called "osTicket" in HeidiSQL. You can do this by right-clicking Unnamed -> Create new -> Database
</p>
<br />

<p>
Go back to the osTicket Installer page and fill out the Database Settings then click "Install Now!"
</p>
<br />

<p>
Enter the database details (MySQL Username: root, MySQL Password: Password1) into the osTicket Installer and click "Install Now!".
</p>
<br />

<p>
Verify the successful installation of osTicket without any errors!
</p>
<br />

<p>
Clean up by deleting the "C:\inetpub\wwwroot\osTicket\setup" folder.
</p>
<br />

<p>
Set the permissions of "C:\inetpub\wwwroot\osTicket\include\ost-config.php" to "Read" only. Right-click "ost-config.php" -> Properties -> Security -> Advanced -> Everyone -> Edit
</p>
<br />

<p>
Navigate to the help desk login page and sign in [http://localhost/osTicket/scp/login.php] using the username and password you created earlier.
</p>
<br />

<p>
Congratulations on completing the lab! We have successfully installed the open-source help desk ticketing system, osTicket!
</p>
<br />
