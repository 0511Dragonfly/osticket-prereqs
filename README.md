<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket. All the files you need to download should be in this google drive link: https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6<br />




<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10 pro</b> (21H2)

<h2>List of Prerequisites</h2>
This list requires downloading and enabling quite a few things to make OS Ticket work how we want it too. You should do these in order if you are following along.

- Enabling IIS (Internet Information Services) in windows along with "Common HTTPS features" and "CGI" in the application development features section of world wide web services, and also enabling the IIS Managment console. You can enable these through the progams section of the control panel
- Download and run PHP Manager for IIS. In my case i used versison 1.5.0 (PHP is a scripting language for web development)
- Download and run ISS URL Rewrite module 2
- Create a folder in the c:\ drive to store the files for PHP 
- Download and run Visual C++ redistributle
- Download mysql server 5.5, use the typical setup when installing, launch the config wizard, install as a widows service and then create whatever password you decide
- we need to register PHP. To do this open IIS manager as an admin, click on PHP Manager and find the clickable text that says "Register new PHP versison" it will then ask you to provide a path to the PHP executable file which we downloading into the PHP folder on the computer. For example the path to the PHP exe file on my VM was "C:\PHP\php-7.3.8-nts-Win32-VC15-x86\php-cgi.exe" after that close and re-open IIS manager then on the right side of the screen restart the server.

  Now we can start downloading OS Ticket

<h2>Installation Steps</h2>
- Once you have installed the OS Ticket zip file, extract the contents of the folder to "C:\inetpub\wwwroot" and rename the "upload" folder to "osTicket"
- Open IIS manager and restart the server again
- Insisde the manager, open the dropdown menus on the left side until you see and click on the folder you named renamed earlier "osTicket" ![image](https://github.com/SeanHardin247/osticket-prereqs/assets/172443627/1e2a195d-0d50-4047-9285-e57fd1c2608c)
-while you have the folder selected on the right of IIS click on "Browse *:80 (http)
- On this page you'll notice some things are missing ![image](https://github.com/SeanHardin247/osticket-prereqs/assets/172443627/0597ee1d-7ade-47e8-aa8b-eafc692ad385) which is mostly fine, but we will fix the PHP one near the top of the list
- To fix this go back to IIS and select the osTicket folder on t he right again, then open PHP manager like last time except this time scroll to the bottom to find PHP Extensions and click "enable or disable an extension"
- The three Extensions in the disabled section you will want to enable are: Enable: php_imap.dll, php_intl.dll and php_opcache.dll. Right click on these and click enable.
- If done correctly then PHP IMAP will show up with a checkmark this time.
- Open file explorer and navigate to C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php and change the name of the "ost-sampleconfig" file to "ost-config"
- Right click on that file and click on the security section then click advanced and disable inheritance at the bottom and remove all. Then click Add and Principal in the select a principle text, type Everyone and press enter or click ok, choose full control permissions and hit ok again. Finally hit apply and then ok to close it.
- We will need to download and run one last thing: HeidiSQL, run through the setup wizard and dont change anything
- Once its done it should have opened, create a new session in the bottom left and make sure the user says "root" if not then input root. In the password part input the same password you used when you setup MySQL then click open
- Minimize heidi and go back to the browser with osTicket installer on it and hit continue until it asks you to fill out the required information, fill it all out until you get to the database settings
- Open heidi again and right click where it says "Unnamed", create, database, and name it osTicket
- Return to the browser again and input "osTicket" in the MySQL Database section, the username should be root, and password shsould be the same one you use in heidi/when you set up MySQL, everything else is fine
- after its done installing there will be some links on the bottom you will want to copy the names dodwn of, these two are your osTicket URL and your staff control panel url.

Congratulations, os ticket is installed, now lets do a little cleaning up before we call it a day

- delete the setup folder in C:\inetpub\wwwroot\osTicket\setup
- go back to C:\inetpub\wwwroot\osTicket\include\ost-config.php in file explorer, right click on the file, properties, security, advancced, select everyone (should be the only principal), edit, and revoke every permission except read, then press ok, and apply

Now we are finished! It was quite the long process but if done right os ticket should be set up and you can start configuring stuff using the urls you should have saved earlier, incase you missed them, they are most likely these two:
http://localhost/osTicket/scp/login.php
http://localhost/osTicket/ 

