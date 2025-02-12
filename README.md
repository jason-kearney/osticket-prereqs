<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop (Windows App)
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Setup a virtual machine in Azure
- Install the osTicket requirements
- Install osTicket itself

<h2>Installation Steps</h2>

![image](https://github.com/user-attachments/assets/3ceca633-7551-40f3-be29-65a07d21ee6b)

<p>
We're first going to create a Windows 10 virtual machine using Azure. We're then going to log into the VM using remote desktop.
</p>
<br />

![image](https://github.com/user-attachments/assets/4e509b0d-6d7c-4f9d-9156-6a273d24d2bc)

<p>
Now we're going to install all of the osTicket requirements. Most of these can be easily installed with the exception of PHP and MySQL. For PHP, create the folder "C:\PHP" and unzip the PHP folder into there. For MySQL, set it up with typical setup and standard configuration. We're also going to install and enable IIS in Windows with CGI so we'll have a web server running for osTicket. We will also register PHP from within IIS and reload the server.
</p>
<br />

![image](https://github.com/user-attachments/assets/37bad2cc-601d-480e-8496-511f894596a3)

<p>
To install osTicket we're going to unzip the osTicket installation folder and move the upload folder into c:\inetpub\wwwroot and rename it to "osTicket". We can then open the osTicket site to complete the installation. We need to enable certain extensions, including php_imap.dll, php_intl.dll, and php_opcache.dll, which can be done from PHP manager. We also need to rename ost-config.php from "C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php" to "C:\inetpub\wwwroot\osTicket\include\ost-config.php". From there, we need to assign permissions to make sure we can make changes to the ost-config file. Strip all of the current permissions away and grant everyone full access. This isn't the best for security reasons, but it helps ensure that this setup works as intended.

</p>
<br />

![image](https://github.com/user-attachments/assets/d6942290-7b11-4e5b-b6d8-a81fbd67a004)

<p>
Fill out the required information to install osTicket. The details of the system settings and admin user don't matter, just remember the username and password for the admin user. We also need to install HeidiSQL so we can make a connection to the database. We're going to create a new session using root as the username and password. From there, create a new database called osTicket. Fill out the database information in the osTicket installation browser using the info we just used with HeidiSQL, namely root for the MySQL database username and password, and osTicket for the MySQL database name. From there you can install now. We can now delete "C:\inetpub\wwwroot\osTicket\setup" and set permissions to “Read” only for "C:\inetpub\wwwroot\osTicket\include\ost-config.php".

</p>
<br />
