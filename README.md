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
Go to Azure and create a Virtual Machine.
<p align="center"><img src="https://i.imgur.com/jM8Cuce.png" height="70%" width="70%" alt="image of creating vm"/> </p>
<p align="center"><img src="https://i.imgur.com/aFVBRqa.png" height="70%" width="70%" alt="image of creating vm"/> </p>
</p>
<br />

<p>
Click "Create New" under the Resource group name and name it "RG-osTicket". Fill out the rest of the settings as done in the pictures below.
<p align="center"><img src="https://i.imgur.com/OJgzTFW.png" height="70%" width="70%" alt="image of creating vm"/> </p>
<p align="center"><img src="https://i.imgur.com/Ae9wOPE.png" height="70%" width="70%" alt="image of creating vm"/> </p>
<p align="center"><img src="https://i.imgur.com/YaRKxGu.png" height="70%" width="70%" alt="image of creating vm"/> </p>
</p>
<br />

<p>
Connect to the Virtual Machine using Remote Desktop by copying and pasting the VM's public IP address into the Remote Desktop Connection window.
  
  Note: Search on your local machine "Remote Desktop Connection" to find the Window
<p align="center"><img src="https://i.imgur.com/hKMXpM1.png" height="70%" width="70%" alt="connecting to vm"/> </p>
<p align="center"><img src="https://i.imgur.com/ppIxZNL.png" height="70%" width="70%" alt="connecting to vm"/> </p>
</p>
<br />

<p>
In the virtual machine, we will begin by installing the Web Platform Installer. Search for "Control Panel" and select "Uninstall a Program" under Programs.
<p align="center"><img src="https://i.imgur.com/EQDat89.png" height="70%" width="70%" alt="installing web platform installer"/> </p>
</p>
<br />

<p>
Enable Internet Information Services (IIS) by selecting "Turn Windows features on or off" in the Control Panel and enabling IIS from the available services. Also make sure to select CGI and Common HTTP Features.
<p align="center"><img src="https://i.imgur.com/gKKvSad.png" height="70%" width="70%" alt="enable iis"/> </p>
<p align="center"><img src="https://i.imgur.com/PF7HKmG.png" height="70%" width="70%" alt="enable iis"/> </p>
<p align="center"><img src="https://i.imgur.com/OyFFTmW.png" height="70%" width="70%" alt="enable iis"/> </p>
</p>
<br />

<p>
Download and install <a href="https://drive.google.com/file/d/1RHsNd4eWIOwaNpj3JW4vzzmzNUH86wY_/view">PHP Manager</a> for IIS.
<p align="center"><img src="https://i.imgur.com/D7LxG6N.png" height="70%" width="70%" alt="download and install php manager"/> </p>
</p>
<br />

<p>
Download and install the <a href="https://drive.google.com/file/d/1tIK9GZBKj1JyUP87eewxgdNqn9pZmVmY/view">Rewrite Module</a>.
<p align="center"><img src="https://i.imgur.com/D3yypus.png" height="70%" width="70%" alt="download and install rewrite module"/> </p>
</p>
<br />

<p>
Create the directory C:\PHP.
<p align="center"><img src="https://i.imgur.com/ztMRhGg.png" height="70%" width="70%" alt="create directory"/> </p>
</p>
<br />

<p>
Download <a href="https://drive.google.com/file/d/1snNMtLdCOpMtkCyD4mvl9yOOmvVIp9fP/view">PHP 7.3.8</a> and unzip the contents into C:\PHP.
<p align="center"><img src="https://i.imgur.com/udR9ME3.png" height="70%" width="70%" alt="download php"/> </p>
<p align="center"><img src="https://i.imgur.com/pN2tsQV.png" height="70%" width="70%" alt="unzip contents"/> </p>
</p>
<br />

<p>
Download and install <a href="https://drive.google.com/file/d/1s1OsGF3-ioO0_9LYizPRiVuIkb3lFJgH/view">VC_redist.x86.exe</a>.
<p align="center"><img src="https://i.imgur.com/2T43bVV.png" height="70%" width="70%" alt="download and install vc"/> </p>
</p>
<br />

<p>
Download and install <a href="https://drive.google.com/file/d/1_OWh9p7VQLcrB0q_V7qT8yHl0xo5gv7z/view">MySQL5.5.62</a>.
<p align="center"><img src="https://i.imgur.com/mpnQ25Q.png" height="70%" width="70%" alt="download and install mysql"/> </p>
<p align="center"><img src="https://i.imgur.com/rN9QtIM.png" height="70%" width="70%" alt="download and install mysql"/> </p>
<p align="center"><img src="https://i.imgur.com/9JO0mdX.png" height="70%" width="70%" alt="download and install mysql"/> </p>
</p>
<br />
  
  
<p>
Launch MySQL to configure and set up credentials.
<p align="center"><img src="https://i.imgur.com/JstuGUv.png" height="70%" width="70%" alt="launch mysql"/> </p>
<p align="center"><img src="https://i.imgur.com/rDO0xOv.png" height="70%" width="70%" alt="launch mysql"/> </p>
<p align="center"><img src="https://i.imgur.com/CMbX64P.png" height="70%" width="70%" alt="launch mysql"/> </p>
</p>
<br />

<p>
Click Start, search for IIS and right click the application to run as administrator.
<p align="center"><img src="https://i.imgur.com/r6HRHhL.png" height="70%" width="70%" alt="search iis"/> </p>
</p>
<br />

<p>
Click on PHP Manager, then "Register new PHP version" and select "php-cgi" in the C:\PHP folder we created earlier.
<p align="center"><img src="https://i.imgur.com/eo3XbQM.png" height="70%" width="70%" alt="register php"/> </p>
<p align="center"><img src="https://i.imgur.com/rFGXCEP.png" height="70%" width="70%" alt="register php"/> </p>
<p align="center"><img src="https://i.imgur.com/0PfpDMm.png" height="70%" width="70%" alt="blank"/> </p>
</p>
<br />

<p>
Click on the name of your server and restart it now.
<p align="center"><img src="https://i.imgur.com/xClQTvS.png" height="70%" width="70%" alt="restart server"/> </p>
</p>
<br />

<p>
Download <a href="https://drive.google.com/file/d/1VeVXKlzHDRjeaVUL99ptq7qYbrbXdFxJ/view?usp=drive_link">osTicket v1.15.8</a>.
<p align="center"><img src="https://i.imgur.com/uhWgSvC.png" height="70%" width="70%" alt="download osticket"/> </p>
</p>
<br />

<p>
Extract and copy "upload" folder in osTicket into C:\inetpub\wwwroot. Rename it "osTicket" after.
<p align="center"><img src="https://i.imgur.com/2WnAuiY.png" height="70%" width="70%" alt="extract upload folder"/> </p>
<p align="center"><img src="https://i.imgur.com/JSsCopj.png" height="70%" width="70%" alt="extract upload folder"/> </p>
</p>
<br />

<p>
Go back to IIS and restart the server again.
<p align="center"><img src="https://i.imgur.com/LFWORqf.png" height="70%" width="70%" alt="restart server"/> </p>
</p>
<br />

<p>
Now in IIS, go to sites -> default -> osTicket. On the right side, click "Browse *80"
<p align="center"><img src="https://i.imgur.com/Kbq8Qsk.png" height="70%" width="70%" alt="browse 80"/> </p>
</p>
<br />

<p>
You should now see the osTicket installer page through the browser window that opens. Review the recommendations/prerequisites.
<p align="center"><img src="https://i.imgur.com/iyWMU2a.png" height="70%" width="70%" alt="osticket installer page"/> </p>
</p>
<br />

<p>
Go back to IIS -> Default -> osTicket, select PHP Manager and enable the required PHP extensions (php_imap.dll, php_intl.dll, php_opcache.dll) for osTicket.
<p align="center"><img src="https://i.imgur.com/CphZ18s.png" height="70%" width="70%" alt="enable php extensions"/> </p>
<p align="center"><img src="https://i.imgur.com/oDsMqLi.png" height="70%" width="70%" alt="enable php extensions"/> </p>
<p align="center"><img src="https://i.imgur.com/vVhXlyn.png" height="70%" width="70%" alt="enable php extensions"/> </p>
<p align="center"><img src="https://i.imgur.com/7QGj249.png" height="70%" width="70%" alt="enable php extensions"/> </p>
<p align="center"><img src="https://i.imgur.com/qiJrxas.png" height="70%" width="70%" alt="enable php extensions"/> </p>
</p>
<br />

<p>
Refresh the osTicket site in the browser to see the changes after enabling the PHP extensions.
<p align="center"><img src="https://i.imgur.com/Mmps4A3.png" height="70%" width="70%" alt="refresh osticket"/> </p>
</p>
<br />

<p>
Rename "ost-sampleconfig.php" to "ost-config.php" in the directory "C:\inetpub\wwwroot\osTicket\include\".
<p align="center"><img src="https://i.imgur.com/En8xreN.png" height="70%" width="70%" alt="rename ost sample config"/> </p>
<p align="center"><img src="https://i.imgur.com/k2rGwET.png" height="70%" width="70%" alt="rename ost sample config"/> </p>
</p>
<br />

<p>
Change the permissions of "ost-config.php" by right-clicking on it, selecting "Properties", navigating to the "Security" tab, clicking on the "Advanced" button, disabling inheritance, removing all inherited permissions, adding new permissions for everyone, and giving full control.
<p align="center"><img src="https://i.imgur.com/Nve1dEj.png" height="70%" width="70%" alt="change permissions"/> </p>
<p align="center"><img src="https://i.imgur.com/M6N5KXO.png" height="70%" width="70%" alt="change permissions"/> </p>
<p align="center"><img src="https://i.imgur.com/pc2zx6I.png" height="70%" width="70%" alt="change permissions"/> </p>
<p align="center"><img src="https://i.imgur.com/B6CWW8M.png" height="70%" width="70%" alt="change permissions"/> </p>
<p align="center"><img src="https://i.imgur.com/ifSGWZH.png" height="70%" width="70%" alt="change permissions"/> </p>
<p align="center"><img src="https://i.imgur.com/WUzUlRW.png" height="70%" width="70%" alt="change permissions"/> </p>
</p>
<br />

<p>
Continue with the osTicket installer in the browser window and fill in the required details on the form up to the Database Settings. Write them down so you do not forget for later!
<p align="center"><img src="https://i.imgur.com/TEQbI5T.png" height="70%" width="70%" alt="osticket installer required details"/> </p>
<p align="center"><img src="https://i.imgur.com/XWKOuKG.png" height="70%" width="70%" alt="osticket installer required details"/> </p>
</p>
<br />

<p>
Download and install <a href="https://docs.google.com/document/d/1WovrX2DaS9xkfaSr4LXyB4YnnWpXIgPCMMbbfgHmGVw/edit?usp=drive_link">HeidiSQL</a> using the provided defaults. This will allow us to connect to the mySQL server and set up a database for osTicket to use.
<p align="center"><img src="https://i.imgur.com/F8gqDg3.png" height="70%" width="70%" alt="download and install heidisql"/> </p>
</p>
<br />

<p>
Open HeidiSQL and create a new session with the username and password you used when setting up the MySQL server. Connect to the session by selecting "Open".
<p align="center"><img src="https://i.imgur.com/1dfMDWQ.png" height="70%" width="70%" alt="create new heidisql session"/> </p>
<p align="center"><img src="https://i.imgur.com/KwYXhnx.png" height="70%" width="70%" alt="create new heidisql session"/> </p>
</p>
<br />

<p>
Create a database called "osTicket" in HeidiSQL. You can do this by right-clicking Unnamed -> Create new -> Database
<p align="center"><img src="https://i.imgur.com/sqMtF5m.png" height="70%" width="70%" alt="create database"/> </p>
<p align="center"><img src="https://i.imgur.com/sFHyZSA.png" height="70%" width="70%" alt="create database"/> </p>
</p>
<br />

<p>
Enter the database details (MySQL Username: root, MySQL Password: Password1) into the osTicket Installer and click "Install Now!".
<p align="center"><img src="https://i.imgur.com/Ub0czGp.png" height="70%" width="70%" alt="database details"/> </p>
</p>
<br />

<p>
Verify the successful installation of osTicket without any errors!
<p align="center"><img src="https://i.imgur.com/FJu5S77.png" height="70%" width="70%" alt="successful osticket installation"/> </p>
</p>
<br />

<p>
Clean up by deleting the "C:\inetpub\wwwroot\osTicket\setup" folder.
<p align="center"><img src="https://i.imgur.com/lP8dtiT.png" height="70%" width="70%" alt="clean up"/> </p>
</p>
<br />

<p>
Set the permissions of "C:\inetpub\wwwroot\osTicket\include\ost-config.php" to "Read" only. Right-click "ost-config.php" -> Properties -> Security -> Advanced -> Everyone -> Edit
<p align="center"><img src="https://i.imgur.com/TEouz1U.png" height="70%" width="70%" alt="set permissions"/> </p>
<p align="center"><img src="https://i.imgur.com/7xX6t3X.png" height="70%" width="70%" alt="set permissions"/> </p>
<p align="center"><img src="https://i.imgur.com/ZdDk9SV.png" height="70%" width="70%" alt="set permissions"/> </p>
<p align="center"><img src="https://i.imgur.com/u7oApT1.png" height="70%" width="70%" alt="set permissions"/> </p>
</p>
<br />

<p>
Navigate to the help desk login page (http://localhost/osTicket/scp/login.php) and sign in using the username and password you created earlier.
<p align="center"><img src="https://i.imgur.com/2Lij66k.png" height="70%" width="70%" alt="help desk login page"/> </p>
</p>
<br />

<p>
Congratulations on completing part 1 of the osTicket lab! We have successfully installed the prerequisites and osTicket!
<p align="center"><img src="https://i.imgur.com/U6o1uK5.png" height="70%" width="70%" alt="part 1 complete"/> </p>
</p>
<br />
