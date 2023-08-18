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


<p>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
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
