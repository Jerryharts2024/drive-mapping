<p align="center">
<img src="https://user-images.githubusercontent.com/131130119/239724733-a34a4353-4aa7-420f-80b5-d1aa414441d7.png" alt="osTicket logo"/>
</p>

<h1>Drive Mapping - Map Network Drive Using Group Policy</h1>
This tutorial outlines prerequisites and implementation of network drive mapping using group policy. To understand drive mapping, kind of think of how files are shared accross different users on the same network. It involves folders, files and even an entire storage drive in a certain Windows computer.Or even cloud storage folder like that of OneDrive. Drive mapping essentially eases to how files are shared to different users connected to one network. It basically means making a specific drive available to other users connected to a common network
    <br />
 
  <h2>Video Demonstration</h2>

- ### [YouTube: How To Install osTicket with Prerequisites](https://youtu.be/0rPyNMxnIKc)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Create an Azure Virtual Machine Windows 10, 4 vCPUs
- Install / Enable IIS in Windows WITH CGI
- install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)
- install the Rewrite Module (rewrite_amd64_en-US.msi)
- Create the directory C:\PHP
- download PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) and unzip the contents into C:\PHP
- download and install VC_redist.x86.exe.
- download and install MySQL 5.5.62 (mysql-5.5.62-win32.msi)
- Open IIS as an Admin and Register PHP from within IIS
- Install osTicket v1.15.8
- Reload IIS (Open IIS, Stop and Start the server)
- Go to sites -> Default -> osTicket (Note that some extensions are not enabled)
- Rename: ost-config.php and Assign Permissions: ost-config.php
- Set up osTicket in the browser (click Continue)
- install HeidiSQL, and Continue Setting up osticket in the browser
- Clean up (Delete: C:\inetpub\wwwroot\osTicket\setup)

