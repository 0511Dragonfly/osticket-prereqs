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

- Enabling IIS (Internet Information Services) in windows along with "Common HTTPS features" and "CGI" in the application development features section of world wide web services, and also enabling the IIS Managment console. You enable these through the progams section of the control panel
- PHP Manager for IIS. In my case i used versison 1.5.0 (PHP is a scripting language for web development)
- ISS URL Rewrite module 2
- Creating a folder in the c:\ drive to store the files for PHP 
- Visual C++ redistributle
- mysql server 5.5, use the typical setup when installing, launch the config wizard, install as a widows service and then create whatever password you decide
- Register PHP. To do this open IIS manager as an admin, click on PHP Manager and find the clickable text that says "Register new PHP versison" it will then ask you to provide a path to the PHP executable file which we downloading into the PHP folder on the computer. For example the path to the PHP exe file on my VM was "C:\PHP\php-7.3.8-nts-Win32-VC15-x86\php-cgi.exe" after that close and re-open IIS manager then on the right side of the screen restart the server.

  Now we can start downloading OS Ticket

<h2>Installation Steps</h2>
- Once you have installed the OS Ticket zip file, move it to "C:\inetpub\wwwroot" and extract it there and rename the "upload" folder to "osTicket"
- Open IIS manager and restart the server again
- Insisde the manager, open the dropdown menus on the left side until you see and click on the folder you named renamed earlier "osTicket" ![image](https://github.com/SeanHardin247/osticket-prereqs/assets/172443627/1e2a195d-0d50-4047-9285-e57fd1c2608c)
-while you have the folder selected on the right of IIS click on "Browse *:80 (http)
- On this page you'll notice some things are missing ![image](https://github.com/SeanHardin247/osticket-prereqs/assets/172443627/0597ee1d-7ade-47e8-aa8b-eafc692ad385) which is mostly fine, but we will fix the PHP one near the top of the list
- To fix this go back to IIS and select the osTicket folder on t he right again, then open PHP manager like last time except this time scroll to the bottom to find PHP Extensions and click "enable or disable an extension"
- The three Extensions in the disabled section you will want to enable are: Enable: php_imap.dll, php_intl.dll and php_opcache.dll. Right click on these and click enable.
- If done creectly 



<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
