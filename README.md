<h1>Active Directory</h1>

<h2>Description</h2>
In this lab I walk through how I created Active Directory home lab Environment using Oracle Virtual Box. Configuring this lab helped further my understanding of how active directory and Windows networking worked.
<br />

<h2>Environments Used </h2>

- <b>Windows 10</b> (21H2)
- <b>Windows Server 19</b>
- <b>Oracle VM VirtualBox</b>

<h2>Program walk-through:</h2>


The picture below is the roadmap I used to complete the lab. <br/>
<img src="https://imgur.com/MsOWxch.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
<br />
<br />
Open VirtualBox and select new. <br/>
<img src="https://imgur.com/XLgm6hV.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
<br />
<br />
Name your Virtual Machine DC. <br/>
Select Other Windows 64-bit for the version, then hit next. <br/>
<img src="https://imgur.com/H6DsLsN.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
<img src="https://imgur.com/oo9OxE3.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
<br />
<br />
Change oyur hardware suitable to your PC setup, hit next. <br/>
<img src="https://imgur.com/F5Ewp6V.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
<br />
<br />
Hit Next. <br/>
Finish. <br/>
<img src="https://imgur.com/RTco81s.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
<img src="https://imgur.com/m7ZKeFk.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
<br />
<br />
While the new virtual machine is highlighted hit Settings. <br/>
<img src="https://imgur.com/V5zlxxk.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
</p>
In General click the Advanced Tab. <br/>
Change Shared Clipboard and Drag'n'Drop to bidirectional. <br/>
<img src="https://i.imgur.com/nCIbXbg.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
<br />
<br />
Click the Network tab. <br/>
Click Adapter 2. Enable it and change Attached to: to Internal network. <br/>
Then click Ok:  <br/>
<img src="https://i.imgur.com/cdFHBiU.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
<br />
<br />
Start the DC machine. <br/>
click the dorp down menu next to DVD. <br/>
Choose the location where you have the Windows Server 2019 ISO file downloaded.  <br/>
<img src="https://i.imgur.com/JL945Ga.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
<br />
<br />
Click Next:  <br/>
<img src="https://i.imgur.com/K71yaM2.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
<br />
<br />
Click CUstom: Install Widnows only (advanced)  <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
</p>
Click Next. <br/>
Allow to install. <br/>
<img src="https://i.imgur.com/nCIbXbg.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
<br />
<br />
You can enter any password but for this lab I kept it simple wiht Password1. <br/>
Login with the Administrator account just created. <br/>
<img src="https://i.imgur.com/cdFHBiU.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
<br />
<br />
Click the computer screen at the bottom right for internet access. <br/>
Click Network & Internet settings. <br/>
<img src="https://i.imgur.com/JL945Ga.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
<br />
<br />
Select Change adapter options.  <br/>
<img src="https://i.imgur.com/K71yaM2.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
<br />
<br />
To identitfy the Internet Network Interface Card(NIC) and the Interal NIC. <br/>
Rigth click the first Ethernet. <br/>
Select Status. <br/>
Select Details. <br/>
This will be our Internet NIC due to the 10.0.2.15 IP Address. <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
</p>
Close this window. <br/>
Click Rename this connection at the top right of the page. <br/>
Rename the Ethernet to something that will help you from misidentifying the port when it comes to configuring them. <br/>
<img src="https://i.imgur.com/nCIbXbg.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
<br />
<br />
Repeat the step above for the next Ethernet. <br/>
This will be our Internal NIC due to the 169.254.210.16 IP Address.  <br/>
Close this screen. <br/>
<img src="https://i.imgur.com/cdFHBiU.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
<br />
<br />
Now, configure the Internal NIC by right clicking it. <br/>
Selecting Properties. <br/>
Double click Internet Protocol Version 4 (TCP/IPv4). <br/>
<img src="https://i.imgur.com/JL945Ga.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
<br />
<br />
Click Use the following IP address. <br/>
Enter the following IP address, Subnet mask and Preferred DNS server. <br/>
Click OK. <br/>
<img src="https://i.imgur.com/K71yaM2.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
<br />
<br />
Click OK and close the window  <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
</p>
Select the Server Manager Application. If you closed this application, just click the maginfy glass at the bottom right of the screen. Type Server Manager and the blue server and gray tool box should appear. <br/>
<img src="https://i.imgur.com/nCIbXbg.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
<br />
<br />
Double click Add roles and features to add Active Directory Domain Services.
Click next 3 times. <br/>
<img src="https://i.imgur.com/cdFHBiU.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
<br />
<br />
Select the box next to Active Directory Domain Services. <br/>
Click Add Features. <br/>
<img src="https://i.imgur.com/JL945Ga.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
<br />
<br />
You will click Next 4 times. <br/>
Click Install. <br/>
<img src="https://i.imgur.com/K71yaM2.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
<br />
<br />
Once the bar below View installation progress is full, click close.  <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
</p>
At the top right corner of "Server Manager", select the flag icon with the yellow triangle sign below it.
Click "Promote this server to a domain controller". <br/>
Select the "Add a new forest" option. You can name the domain whatever you like. For this lab I kept it simple with "mydomain.com". <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
</p>
Click Next. <br/>
Add a password. <br/>
Then, click next 5 times. <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
</p>
Click Install. <br/>
Your virtual machine will restart on its own. <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
</p>
On the login screen you should see "MYDOMAIN\Administrator". <br/>
Login with the password you created. <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
</p>
Click the Windows Icon at the bottom left of the screen. <br/>
Under the Windows Administrative Tools tab, select the "Active Directory Users and Computers". <br/>
<img src="https://i.imgur.com/nCIbXbg.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
<br />
<br />
Rigth click "mydomain.com". <br/>
Hover over "New". <br/>
Then select "Organizational Unit". <br/>
<img src="https://i.imgur.com/cdFHBiU.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
<br />
<br />
Name it "_ADMIN". This will be the folder for your administrative accounts. <br/>
Click "OK". <br/>
<img src="https://i.imgur.com/JL945Ga.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
<br />
<br />
After creating the "_ADMIN" foldear, right click it. <br/>
Hover over "New". <br/>
Click "User". <br/>
<img src="https://i.imgur.com/K71yaM2.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
<br />
<br />
Fill in your "First" and "Last" name. <br/>
For "User logon name:" put "a-first Initial + last name" as shown in the picture. <br/>
Then press Next. <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
</p>
Create a password. <br/>
Check the box next to "Password never expires" and click next. <br/>
Click Finish. <br/>
<img src="https://i.imgur.com/nCIbXbg.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
<br />
<br />
Go to the "_ADMIN" folder and double click the new admin user. <br/>
Click the "Member Of" tab. <br/>
In the "Enter the object names to select", tpye "Domain Admins". Then click Check Names and OK. <br/>
<img src="https://i.imgur.com/cdFHBiU.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
<br />
<br />
Open the Server Manager application. <br/>
Click "Add roles and features", click next 3 times. <br/>
Select the box next to "Remote Access". <br/>
<img src="https://i.imgur.com/JL945Ga.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
<br />
<br />
Click next 2 times. <br/>
Select the box next to "Routing". <br/>
Click "Add Features". Both "Routing" and "DirectAccess and VPN" will be selected. <br/>
<img src="https://i.imgur.com/K71yaM2.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
<br />
<br />
Clict next 3 times. <br/>
Click Install. <br/>
Click Close. <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
</p>
Go back to the Server Manager. In the top right corner select "Tools". <br/>
Select "Routing and Remote Access". <br/>
Right click "DC(local)" and select "Configure and Enable Routing and Remote Access". <br/>
<img src="https://i.imgur.com/nCIbXbg.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
<br />
<br />
Click next. <br/>
Select the "Network address Translation (NAT)". This is how you will connect to the Internet. <br/>
Click next 2 times and then finish. <br/>
<img src="https://i.imgur.com/cdFHBiU.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
<br />
<br />
Open Server Mananger. <br/>
Select "Add roles and features". Click next 3 times. <br/>
On Server Roles, select "DHCP Server" and then next. <br/>
<img src="https://i.imgur.com/JL945Ga.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
<br />
<br />
You will click next 3 times. <br/>
Click Install. <br/>
In Server Manager, select "Tools" and click "DHCP". <br/>
<img src="https://i.imgur.com/K71yaM2.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
<br />
<br />
Right click IPv4. Select "New Scope.." and click next. <br/>
Input 172.16.0.100 for the Start IP address. <br/>
Input 172.16.0.200 for End IP address. Click next.<br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
</p>
Click next 3 times. <br/>
Input 172.16.0.1 then click "Add". <br/>
Click next 4 times and then finish.<br/>
<img src="https://i.imgur.com/nCIbXbg.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
<br />





##CLIENT!##





<br />
Double click Add roles and features to add Active Directory Domain Services.
Click next.
Next. <br/>
<img src="https://i.imgur.com/cdFHBiU.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
<br />
<br />
Next.
Select the box next to Active Directory Domain Services.
Click Add Features.<br/>
<img src="https://i.imgur.com/JL945Ga.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
<br />
<br />
You will click Next 4 times.
Click Install.
<br/>
<img src="https://i.imgur.com/K71yaM2.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
<br />
<br />
Once the bar below View installation progress is full, click close.  <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
</p>
Select the Server Manager Application. If you closed this application, just click the maginfy glass at the bottom right of the screen. Type Server Manager and the blue server and gray tool box should appear. <br/>
<img src="https://i.imgur.com/nCIbXbg.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
<br />
<br />
Double click Add roles and features to add Active Directory Domain Services.
Click next.
Next. <br/>
<img src="https://i.imgur.com/cdFHBiU.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
<br />
<br />
Next.
Select the box next to Active Directory Domain Services.
Click Add Features.<br/>
<img src="https://i.imgur.com/JL945Ga.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
<br />
<br />
You will click Next 4 times.
Click Install.
<br/>
<img src="https://i.imgur.com/K71yaM2.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
<br />
<br />
Once the bar below View installation progress is full, click close.  <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
</p>
<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
