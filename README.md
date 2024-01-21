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

- Create an Azure Virtual Machine Windows 10, 4 vCPUs
- Install / Enable IIS in Windows WITH
CGI and Common HTTP Features
- Download and install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)
- Download and install the Rewrite Module (rewrite_amd64_en-US.msi)
- Download PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) and unzip the contents into C:\PHP
- Download and install VC_redist.x86.exe.
- Download and install MySQL 5.5.62 (mysql-5.5.62-win32.msi)
- Open IIS as an Admin
- Register PHP from within IIS
- Reload IIS (Open IIS, Stop and Start the server)
- Install osTicket v1.15.8
- Download and install HeidiSQL.
-Install osTicket and browse to your helpdesk login page

<h2>Installation Steps</h2>

<p>
<img src="https://i.imgur.com/oBY9bnF.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/RChaxRs.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Install / Enable IIS in Windows WITH
CGI and Common HTTP Features
World Wide Web Services -> Application Development Features ->
[X] CGI
[X] Common HTTP Features
AND IIS Management Console
Internet Information Services -> Web Management Tools -> IIS Management Console
	[X] IIS Management Console

</p>
<br />

<p>
<img src="https://i.imgur.com/l21rcJM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Download and install MySQL 5.5.62 (mysql-5.5.62-win32.msi)
Typical Setup ->
Launch Configuration Wizard (after install) ->
Standard Configuration ->
set password

Open IIS as an Admin

Register PHP from within IIS

Reload IIS (Open IIS, Stop and Start the server)

Install osTicket v1.15.8
Download osTicket from the Installation Files Folder
Extract and copy “upload” folder to c:\inetpub\wwwroot
Within c:\inetpub\wwwroot, Rename “upload” to “osTicket”

Reload IIS (Open IIS, Stop and Start the server)

Go to sites -> Default -> osTicket
On the right, click “Browse *:80”

Note that some extensions are not enabled
Go back to IIS, sites -> Default -> osTicket
Double-click PHP Manager
Click “Enable or disable an extension”
Enable: php_imap.dll
Enable: php_intl.dll
Enable: php_opcache.dll
Refresh the osTicket site in your browse, observe the changes

Rename: ost-config.php
From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
To: C:\inetpub\wwwroot\osTicket\include\ost-config.php

Assign Permissions: ost-config.php
Disable inheritance -> Remove All
New Permissions -> Everyone -> All

Continue Setting up osTicket in the browser (click Continue)
Name Helpdesk
Default email (receives email from customers)

From the Installation Files, download and install HeidiSQL.
Open Heidi SQL
Create a new session, root/set password
Connect to the session
Create a database called “osTicket”

Continue Setting up osticket in the browser
MySQL Database: osTicket
MySQL Username: root
MySQL Password: enter password
Click “Install Now!”

</p>
<br />

<p>
<img src="https://i.imgur.com/CiWmE6F.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Browse to your help desk login page: http://localhost/osTicket/scp/login.php

End Users osTicket URL:
http://localhost/osTicket/ 

Clean up
Delete: C:\inetpub\wwwroot\osTicket\setup
Set Permissions to “Read” only: C:\inetpub\wwwroot\osTicket\include\ost-config.php

Notes:
Browse to your help desk login page: http://localhost/osTicket/scp/login.php  
End Users osTicket URL: http://localhost/osTicket/ 

</p>
<br />
