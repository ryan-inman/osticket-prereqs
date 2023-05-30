<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How To Install osTicket with Prerequisites](https://www.youtube.com)

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
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Go to Azure and create a Virtual Machine
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Click "Create New" under the Resource group name and name it "RG-osTicket". Fill out the rest of the settings as done in the pictures below.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Connect to the Virtual Machine using Remote Desktop by copying and pasting the VM's public IP address into the Remote Desktop Connection window.
  
  Note: Search on your local machine "Remote Desktop Connection" to find the Window
</p>
<br />

<p>
Install the Web Platform Installer by searching for "Control Panel" and selecting "Uninstall a Program" under Programs.

</p>
<br />

<p>
Enable Internet Information Services (IIS) by selecting "Turn Windows features on or off" in the Control Panel and enabling IIS from the available services. Also make sure to select CGI and Common HTTP Features.

</p>
<br />

Download and install Web Platform Installer (WebPI), which simplifies the installation of web applications and platform technologies.
</p>
<br />

<p>
Download and install MySQL 5.5 database, PHP 5.6.31, and versions between PHP (x86) 7.0 and 7.3 using WebPI.
</p>
<br />

<p>
Extract the osTicket files and copy the "upload" folder to "c:\inetpub\wwwroot". Rename the "upload" folder to "osTicket".
</p>
<br />

<p>
Restart IIS by going to Sites -> Default -> osTicket and clicking on Browse *:80.
</p>
<br />

<p>
Access the osTicket installer page through the browser window that opens and review the recommendations/prerequisites.
</p>
<br />

<p>
Go back to IIS and enable the required PHP extensions (php_imap.dll, php_intl.dll, php_opcache.dll) for osTicket.
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
Continue with the osTicket installer in the browser window and fill in the required details on the form.
</p>
<br />

<p>
Download and install HeidiSQL using the provided defaults.
</p>
<br />

<p>
Open HeidiSQL and create a new session with the username "root" and password "Password1". Connect to the session.
</p>
<br />

<p>
Create a database called "osTicket" in HeidiSQL.
</p>
<br />

<p>
Enter the database details (MySQL Username: root, MySQL Password: Password1) into the osTicket Installer and click "Install Now!".
</p>
<br />

<p>
Verify the successful installation of osTicket without any errors.
</p>
<br />

<p>
Choose between accessing the Admin login or the End User Portal for osTicket based on the provided links.
</p>
<br />

<p>
Clean up by deleting the "C:\inetpub\wwwroot\osTicket\setup" folder.
</p>
<br />

<p>
Set the permissions of "C:\inetpub\wwwroot\osTicket\include\ost-config.php" to "Read" only.
</p>
<br />

<p>
Login to the osTicket Admin Panel at [http://localhost/osTicket/scp/login.php](http://localhost/osTicket/scp/login.php).
</p>
<br />

<p>
Congratulations on completing the lab!
</p>
