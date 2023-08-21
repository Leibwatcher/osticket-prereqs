<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Video Demonstration</h2>



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Connect to your Virtaul Machine with Remote Desktop
- install / Enable IIS in Windows
- HeidiSQL_12.3.0.6589_setup.exe
- osTicket-v1.15..8.zip
- php-7.3.8-nts-Win32-VC15-x86.zip
- php-ManagerForIIS_v1.5.0.msi
- rewrite_amd64_en-US.msi
- VC_redist.x86.exe
- clean up
- Change File Permissions

<h2>Installation Steps</h2>

I Created and started up a virtual machine, the resource group can be created my selecting "create New" to make the resource group and I named it "osTicket_practice" but it can be named anything. Then I set it up to my Virtual Machine(VM) and selected the appropriate setting. 

![Screenshot 2023-07-31 183738](https://github.com/Leibwatcher/osticket-prereqs/assets/137578446/d0218aa4-4cc3-4d07-9f79-0895fcca1ff5)


I created a username and password and then by selecting "I confirm I have an eligible Windows 10/11 liceense with multi-tenant hosting rights" then review+create to proceed.
![Screenshot 2023-07-31 184056](https://github.com/Leibwatcher/osticket-prereqs/assets/137578446/f8519d40-4dd1-4bb0-b06f-109b1a904efd)
 

To get inside of our Vitrual mchine(VM), We'll need to connect our virtual machine(VM) with Remote Desktop by using the VM's public Ip address. Going to start search "Remote Desktop Connection" and copy the Public IP Address and paste it in computer in Remote Desktop Connections and and click on connect. 

![Screenshot 2023-07-30 095720](https://github.com/Leibwatcher/osticket-prereqs/assets/137578446/f26aa11b-4764-4d59-8e36-43be7a869ed8)


After connecting to your Virtual Machine, we'll need to install Web Platform Installer. So head to start and search for Control Panel.....under program select Uninstall a Program.
![Annotation 2023-07-31 224722](https://github.com/Leibwatcher/osticket-prereqs/assets/137578446/13f53c82-b02e-4620-863e-82830588c2f3)

Click on "Turn Windows Features On Or Off" then find and enable the "Internet Infomation Services" IIS from available services. Click on + on IIS and enable "World Wide Web Services" then + on World Wide Web Services and check "CGI" then click "OK"

![Annotation 2023-07-31 225444](https://github.com/Leibwatcher/osticket-prereqs/assets/137578446/2b882dbc-d982-4574-ac41-1b32bac0e712)

Next, getting PHP manger file for istall a IIS setup wizard. Going through the setup, there is no need to change anything just keep all default settings and contuinue with "next" and than "install" 

![Annotation 2023-07-31 230606](https://github.com/Leibwatcher/osticket-prereqs/assets/137578446/9d4268a6-54dc-4a7a-adc1-fb1757a4a05c)

After the PHP manger is in stalled, next is to install the "ISS URL Rewrite Module" Same thing click next and keep all defualt settings
![Annotation 2023-07-31 230649](https://github.com/Leibwatcher/osticket-prereqs/assets/137578446/c7bc0d4d-d33a-45df-b4f2-168358e9b458)

Create a new file for PHP in the C: drive. "C:\PHP" Then I installed PHP 7.3.8(php-7.3.8-nts-Win32-VC15-x86.zip) and unzip the file into the C:\PHP folder.

![Screenshot 2023-07-31 190916](https://github.com/Leibwatcher/osticket-prereqs/assets/137578446/2821a247-220d-471a-a9a5-c00bba47c189)

Once VC_redist.x86.exe, then I install MySQL 5.5.62(mysql-5.5.62-win32.msi) right away. I didnt do anything special I clicked on "Typical Setup" next "Launch Configuration Wizard(after install)
"Standard Configuration" then I set my password.

![Annotation 2023-07-31 231140](https://github.com/Leibwatcher/osticket-prereqs/assets/137578446/6225fb84-f5f2-400d-9ea8-c3eb3025a44a)

![Screenshot 2023-07-31 191316](https://github.com/Leibwatcher/osticket-prereqs/assets/137578446/5c0c93c2-16b4-4311-9793-4ce2d7ac60de)

Open "Internet Information Service(IIS)" as Administrator
![Screenshot 2023-07-31 191558](https://github.com/Leibwatcher/osticket-prereqs/assets/137578446/70aa8938-372b-44e2-90b5-5e2f4666a431)

I register PHP within the IIS and then restarted IIS by clicking reload, or stop and start.

![Screenshot 2023-07-31 191703](https://github.com/Leibwatcher/osticket-prereqs/assets/137578446/5dbeac36-9f17-4edb-bb5c-1136ec592e8d)

This is the time we can install "OsTicket" after OsTickv1.15.8 is installed, go and exctract and copy "upload" folder into c:\inetpub\wwwroot. While you're within the folder c:\inetpub\wwwroot, then rename the "upload" folder to "osTicket".

![Screenshot 2023-07-31 192024](https://github.com/Leibwatcher/osticket-prereqs/assets/137578446/a52d6e1d-51c7-45ba-8d65-bcad67f821ff)

![Screenshot 2023-07-31 192519](https://github.com/Leibwatcher/osticket-prereqs/assets/137578446/d15da144-899c-438b-b663-5d4147336e7b)


Reload IIS! To the left click on "Browse *:80" Click on "Sites" then "Default" and finally "osticket" Then in the PHP you can see some extensions are enabled and some are not. We have to enable 3 extensions Click on to enable "php_imap.dll" "php_intl.dll" and "php_opcache.dll"


![Screenshot 2023-07-31 192305](https://github.com/Leibwatcher/osticket-prereqs/assets/137578446/17abdfae-c933-4440-8d68-2ff262118ee6)

Refresh and see the the red X's change to grean check marks.
![Screenshot 2023-07-31 192158](https://github.com/Leibwatcher/osticket-prereqs/assets/137578446/2e694011-6244-49a1-8111-2fd789f4c994)

![Screenshot 2023-07-31 192158](https://github.com/Leibwatcher/osticket-prereqs/assets/137578446/11811159-29b8-41cd-9121-0654bf84e58a)

<p>
</p>
<p>

</p>
<br />



<p>
<img src="https://![image](https://github.com/Leibwatcher/osticket-prereqs/assets/137578446/f75b6946-e8b1-499d-90ee-4fdfe7bb61a2)
" height="80%" width="80%" alt="Disk Sanitization Steps"/>
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
