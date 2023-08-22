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

![Screenshot 2023-07-31 192850](https://github.com/Leibwatcher/osticket-prereqs/assets/137578446/f5503229-9830-4a93-9c64-433c0884bf75)

From the file C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php and rename to C:\inetpub\wwwroot\osTicket\include\ost-config.php
![Screenshot 2023-07-31 192620](https://github.com/Leibwatcher/osticket-prereqs/assets/137578446/90012561-acba-4792-a43e-bddb0f21e295)

I went to properties on the PHP file properties. Then I clicked the Security tab, Systems, and then Advanced tab. From there a "block Inheritance" window will appear. Clicking on "Remove all inherited permissions from this object. I enter "Everyone" in the object name box. Check name then ok. Give everyone "Full control" and click ok.

![Screenshot 2023-07-31 192803](https://github.com/Leibwatcher/osticket-prereqs/assets/137578446/676b8f97-512b-40f0-8058-04ccd9ae867c)

Now we can return to the browser windows with osTicket and clcik "Continue" and you'll see a form to be completed for your account.
![Screenshot 2023-07-31 193020](https://github.com/Leibwatcher/osticket-prereqs/assets/137578446/a2e7405e-9bb7-49c7-b2f1-54c39bde35de)


The next step after completing the form on osTicket. We can start downloading "HeidiSQL" Click on "I agree" and continue through the setup. 
![Annotation 2023-07-31 233407](https://github.com/Leibwatcher/osticket-prereqs/assets/137578446/33a10d88-150c-4ffe-8dd3-f21f6da5cca2)

This is where you'll create an user name and password for the account for your osticketing system.  Clcik on new on the bottom left and open, then right-click on "unnamed" click on "create new" and "database"

![Annotation 2023-07-31 233722](https://github.com/Leibwatcher/osticket-prereqs/assets/137578446/45e78c6d-bd28-4711-83d5-eb885430ba58)

Then after creating the database, appy the info you created into "MySQL" then click "Install now". You should see this screen hopefully no error messages.
![Annotation 2023-07-31 234024](https://github.com/Leibwatcher/osticket-prereqs/assets/137578446/7487e107-bccb-47d1-8677-89f9c3fb7334)

![Annotation 2023-08-06 173122](https://github.com/Leibwatcher/osticket-prereqs/assets/137578446/aefb489a-e4b8-4f6f-81dd-d0914e3f21f7)


http://localhost/osTicket/scp/login.php appy this to your URL and i'll take you a support center. Here you'll "Open A New Ticket" and "Check Ticket Status"

![Screenshot 2023-08-06 141840](https://github.com/Leibwatcher/osticket-prereqs/assets/137578446/da7c6e0f-549f-4a97-ae4c-3b7847a87bf1)

Clean up: First, delete "C:\inetpub\wwwroot\osTicket\setup". Secondly, back to "C:\inetpub\wwwroot\osTicket\include\ost-config.php" set Permissions to "READ" only and lastly long into osTicket Admin Panel.
![Annotation 2023-07-31 234113](https://github.com/Leibwatcher/osticket-prereqs/assets/137578446/8298addd-837e-4a09-82c0-e22e55570f29)

![Screenshot 2023-07-31 192620](https://github.com/Leibwatcher/osticket-prereqs/assets/137578446/b518a08e-d68b-4ef6-8d79-65b137f78579)

           !That all the steps to set up osTicket and Congratulations on achievment completion of this lab!
<p>
</p>
<p>

</p>
<br />

</p>
<br />
