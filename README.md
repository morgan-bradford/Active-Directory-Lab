<h1>Active Directory</h1>

<h2>Description</h2>
In this lab, I walk through how I created Active Directory home lab environment using Oracle Virtual Box. Configuring this lab helped further my understanding of how active directory and Windows networking worked.
<br />

<h2>Environments Used </h2>

- <b>Windows 10 (21h2): <b/> https://www.microsoft.com/en-us/software-download/windows10
- <b>Windows Server 19:</b> https://www.microsoft.com/en-us/evalcenter/download-windows-server-2019
- <b>Oracle VM VirtualBox:</b> https://www.virtualbox.org/wiki/Downloads
  
<h2>Program walk-through:</h2>


The picture below is the roadmap I used to complete the lab. <br/>
Before starting you will need to download Windows 10 and Windows server 2019 ISO. <br/>
<img src="https://imgur.com/MsOWxch.png" height="75%" width="75%" alt="Active Directory Steps"/>
<br />
<br />
Open VirtualBox and select "New". <br/>
<img src="https://imgur.com/XLgm6hV.png" height="75%" width="75%" alt="Active Directory Steps"/>
<br />
<br />
Name your virtual machine "DC". <br/>
Select "Other Windows (64-bit)" for the version, then click "Next". <br/>
<img src="https://imgur.com/H6DsLsN.png" height="75%" width="75%" alt="Active Directory Steps"/>
<img src="https://imgur.com/oo9OxE3.png" height="75%" width="75%" alt="Active Directory Steps"/>
<br />
<br />
Change your hardware suitable to your PC setup, click "Next". <br/>
<img src="https://imgur.com/F5Ewp6V.png" height="75%" width="75%" alt="Active Directory Steps"/>
<br />
<br />
Click "Next". <br/>
Click "Finish". <br/>
<img src="https://imgur.com/RTco81s.png" height="75%" width="75%" alt="Active Directory Steps"/>
<img src="https://imgur.com/m7ZKeFk.png" height="75%" width="75%" alt="Active Directory Steps"/>
<br />
<br />
While the new virtual machine is highlighted hit "Settings". <br/>
<img src="https://imgur.com/V5zlxxk.png" height="75%" width="75%" alt="Active Directory Steps"/>
</p>
In General click the "Advanced" Tab. <br/>
Change "Shared Clipboard and Drag'n'Drop" to "bidirectional". <br/>
<img src="https://imgur.com/utrF9vb.png" height="75%" width="75%" alt="Active Directory Steps"/>
<img src="https://imgur.com/AjxvRmw.png" height="75%" width="75%" alt="Active Directory Steps"/>
<br />
<br />
Click the "Network" tab. <br/>
Click Adapter 2. Enable it and change "Attached to" to Internal network. <br/>
Then click "OK"  <br/>
<img src="https://imgur.com/Ca5YQ18.png" height="75%" width="75%" alt="Active Directory Steps"/>
<br />
<br />
Start the DC machine. <br/>
Click the drop down menu next to "DVD". <br/>
Choose the location where you have the Windows Server 2019 ISO file downloaded.  <br/>
<img src="https://imgur.com/rEDIdHq.png" height="75%" width="75%" alt="Active Directory Steps"/>
<img src="https://imgur.com/aZ08eWZ.png" height="75%" width="75%" alt="Active Directory Steps"/>
<br />
<br />
Click Next. <br/>
<img src="https://imgur.com/ymsReKl.png" height="75%" width="75%" alt="Active Directory Steps"/>
<br />
<br />
Click "Custom Install Windows only (advanced)". <br/>
<img src="https://imgur.com/wx5jebL.png" height="75%" width="75%" alt="Active Directory Steps"/>
</p>
Click Next. <br/>
Allow to install. <br/>
<img src="https://imgur.com/XHM2Mtk.png" height="75%" width="75%" alt="Active Directory Steps"/>
<img src="https://imgur.com/iTBlL5q.png" height="75%" width="75%" alt="Active Directory Steps"/>
<br />
<br />
You can enter any password. For this lab I kept it simple wiht Password1. <br/>
Login with the Administrator account just created. <br/>
<img src="https://imgur.com/FuPT5QE.png" height="75%" width="75%" alt="Active Directory Steps"/>
<img src="https://imgur.com/TnfgpuD.png" height="75%" width="75%" alt="Active Directory Steps"/>
<br />
<br />
Click the computer screen at the bottom right for internet access. <br/>
Click "Network & Internet settings". <br/>
<img src="https://imgur.com/hT1LZYJ.png" height="75%" width="75%" alt="Active Directory Steps"/>
<img src="https://imgur.com/jHobDrB.png" height="75%" width="75%" alt="Active Directory Steps"/>
<br />
<br />
Select "Change adapter options".  <br/>
<img src="https://imgur.com/qnA1BHj.png" height="75%" width="75%" alt="Active Directory Steps"/>
<br />
<br />
To identitfy the Internet Network Interface Card(NIC) and the Interal NIC. <br/>
Rigth click the first Ethernet. <br/>
Select "Status". <br/>
Select "Details". <br/>
This will be our Internet NIC due to the "10.0.2.15" IP Address. <br/>
<img src="https://imgur.com/Xphtj7g.png" height="75%" width="75%" alt="Active Directory Steps"/>
<img src="https://imgur.com/j5WqXad.png" height="75%" width="75%" alt="Active Directory Steps"/>
<img src="https://imgur.com/VUFadkZ.png" height="75%" width="75%" alt="Active Directory Steps"/>
</p>
Close this window. <br/>
Click "Rename this connection" at the top right of the page. <br/>
Rename the Ethernet to something that will help you from misidentifying the port when it comes to configuring them. <br/>
<img src="https://imgur.com/j1xNCe4.png" height="75%" width="75%" alt="Active Directory Steps"/>
<img src="https://imgur.com/3yvG0Ln.png" height="75%" width="75%" alt="Active Directory Steps"/>
<br />
<br />
Repeat the step above for the next Ethernet. <br/>
This will be our Internal NIC due to the "169.254.210.16" IP address.  <br/>
Close this screen. <br/>
<img src="https://imgur.com/TKVpOGW.png" height="75%" width="75%" alt="Active Directory Steps"/>
<img src="https://imgur.com/BR6WDuu.png" height="75%" width="75%" alt="Active Directory Steps"/>
<br />
<br />
Now, configure the Internal NIC by right clicking it. <br/>
Select "Properties". <br/>
Double click "Internet Protocol Version 4 (TCP/IPv4)". <br/>
<img src="https://imgur.com/JIGLkHC.png" height="75%" width="75%" alt="Active Directory Steps"/>
<img src="https://imgur.com/0uoCD4U.png" height="75%" width="75%" alt="Active Directory Steps"/>
<br />
<br />
Click Use the following IP address. <br/>
Enter the IP address, Subnet mask and Preferred DNS server following the picture below. <br/>
Click "OK". <br/>
<img src="https://imgur.com/rijNnzL.png" height="75%" width="75%" alt="Active Directory Steps"/>
<br />
<br />
Click "OK" and close the window  <br/>
</p>
Select the Server Manager Application. If you closed this application, just click the maginfy glass at the bottom right of the screen. Type Server Manager and the blue server with a gray tool box should appear. <br/>
Double click Add roles and features to add Active Directory Domain Services.
Click next 3 times. <br/>
<img src="https://imgur.com/BMu5P4I.png" height="75%" width="75%" alt="Active Directory Steps"/>
<img src="https://imgur.com/XmiMYp2.png" height="75%" width="75%" alt="Active Directory Steps"/>
<img src="https://imgur.com/lifhHwb.png" height="75%" width="75%" alt="Active Directory Steps"/>
<img src="https://imgur.com/mYUSXwI.png" height="75%" width="75%" alt="Active Directory Steps"/>
<br />
<br />
Select the box next to Active Directory Domain Services. <br/>
Click Add Features. <br/>
<img src="https://imgur.com/zKXV5Rx.png" height="75%" width="75%" alt="Active Directory Steps"/>
<img src="https://imgur.com/HqgdgqF.png" height="75%" width="75%" alt="Active Directory Steps"/>
<br />
<br />
You will click Next 3 times. <br/>
Click Install. <br/>
<img src="https://imgur.com/S6zzwKb.png" height="75%" width="75%" alt="Active Directory Steps"/>
<img src="https://imgur.com/bJk0qfv.png" height="75%" width="75%" alt="Active Directory Steps"/>
<img src="https://imgur.com/iI8XYIS.png" height="75%" width="75%" alt="Active Directory Steps"/>
<br />
<br />
Once the bar below "View installation progress" is full, click close.  <br/>
<img src="https://imgur.com/HPinLL2.png" height="75%" width="75%" alt="Active Directory Steps"/>
</p>
At the top right corner of Server Manager, select the flag icon with the yellow triangle sign below it.
Click "Promote this server to a domain controller". <br/>
Select the "Add a new forest" option. You can name the domain whatever you like. For this lab I kept it simple with "mydomain.com". <br/>
<img src="https://imgur.com/raOEYVm.png" height="75%" width="75%" alt="Active Directory Steps"/>
<img src="https://imgur.com/s7loX4z.png" height="75%" width="75%" alt="Active Directory Steps"/>
<img src="https://imgur.com/XGcw4IZ.png" height="75%" width="75%" alt="Active Directory Steps"/>
</p>
Click Next. <br/>
Add a password. <br/>
Then, click next 5 times. <br/>
<img src="https://imgur.com/nfhLSel.png" height="75%" width="75%" alt="Active Directory Steps"/>
<img src="https://imgur.com/eDOEY8y.png" height="75%" width="75%" alt="Active Directory Steps"/>
<img src="https://imgur.com/lJ1YjYB.png" height="75%" width="75%" alt="Active Directory Steps"/>
<img src="https://imgur.com/7KMtJbI.png" height="75%" width="75%" alt="Active Directory Steps"/>
<img src="https://imgur.com/lKnpZcx.png" height="75%" width="75%" alt="Active Directory Steps"/>
</p>
Click Install. <br/>
Your virtual machine will restart on its own. <br/>
<img src="https://imgur.com/WZIeli0.png" height="75%" width="75%" alt="Active Directory Steps"/>
</p>
On the login screen you should see "MYDOMAIN\Administrator". <br/>
Login with the password you created. <br/>
<img src="https://imgur.com/W9Q8v34.png" height="75%" width="75%" alt="Active Directory Steps"/>
</p>
Click the Windows icon at the bottom left of the screen. <br/>
Under the Windows "Administrative Tools" tab, select the "Active Directory Users and Computers". <br/>
<img src="https://imgur.com/WxvGM9l.png" height="75%" width="75%" alt="Active Directory Steps"/>
<br />
<br />
Rigth click "mydomain.com". <br/>
Hover over "New". <br/>
Then select "Organizational Unit". <br/>
<img src="https://imgur.com/tFpKRnp.png" height="75%" width="75%" alt="Active Directory Steps"/>
<br />
<br />
Name it "_ADMIN". This will be the folder for your administrative accounts. <br/>
Click "OK". <br/>
<img src="https://i.imgur.com/JL945Ga.png" height="75%" width="75%" alt="Active Directory Steps"/>
<br />
<br />
After creating the "_ADMIN" foldear, right click it. <br/>
Hover over "New". <br/>
Click "User". <br/>
<img src="https://imgur.com/q7qzTrC.png" height="75%" width="75%" alt="Active Directory Steps"/>
<img src="https://imgur.com/kkib4EP.png" height="75%" width="75%" alt="Active Directory Steps"/>
<br />
<br />
Fill in your "First" and "Last" name. <br/>
For "User logon name:" put "a-first Initial + last name" as shown in the picture. <br/>
Then press Next. <br/>
<img src="https://imgur.com/Dly1nDh.png" height="75%" width="75%" alt="Active Directory Steps"/>
</p>
Create a password. <br/>
Check the box next to "Password never expires" and click next. <br/>
Click Finish. <br/>
<img src="https://imgur.com/EDG6wbG.png" height="75%" width="75%" alt="Active Directory Steps"/>
<img src="https://imgur.com/YaBRRJ4.png" height="75%" width="75%" alt="Active Directory Steps"/>
<br />
<br />
Go to the "_ADMIN" folder and double click the new admin user. <br/>
Click the "Member Of" tab. <br/>
In the "Enter the object names to select", tpye "Domain Admins". Then click "Check Names" and "OK". <br/>
<img src="https://imgur.com/TPbvJVr.png" height="75%" width="75%" alt="Active Directory Steps"/>
<img src="https://imgur.com/WguTXaE.png" height="75%" width="75%" alt="Active Directory Steps"/>
<br/>
<br/>
Click the Windows icon in the bottom left of the screen. <br/>
Click in the Person icon. <br/>
Select Sign out. <br/>
<img src="https://imgur.com/XwiNluI.png" height="75%" width="75%" alt="Active Directory Steps"/>
<br />
<br />
Select Other user in the bottom left corner and sign in using the admin account you created. <br/>
<img src="https://imgur.com/Qe5iBr5" height="75%" width="75%" alt="Active Directory Steps"/>
<br/>
<br/>
Open the Server Manager application. <br/>
Click "Add roles and features", click next 3 times. <br/>
Select the box next to "Remote Access". <br/>
<img src="https://imgur.com/3sOS65T.png" height="75%" width="75%" alt="Active Directory Steps"/>
<img src="https://imgur.com/vDc3lvH.png" height="75%" width="75%" alt="Active Directory Steps"/>
<br />
<br />
Click next 2 times. <br/>
Select the box next to "Routing". <br/>
Click "Add Features". Both "Routing" and "DirectAccess and VPN" will be selected. <br/>
<img src="https://imgur.com/2vcWs8R.png" height="75%" width="75%" alt="Active Directory Steps"/>
<img src="https://imgur.com/63tLbnX.png" height="75%" width="75%" alt="Active Directory Steps"/>
<img src="https://imgur.com/vtgOaNP.png" height="75%" width="75%" alt="Active Directory Steps"/>
<br />
<br />
Clict next 3 times. <br/>
Click Install. <br/>
Click Close. <br/>
<img src="https://imgur.com/x27NK3r.png" height="75%" width="75%" alt="Active Directory Steps"/>
</p>
Go back to the Server Manager. In the top right corner select "Tools". <br/>
Select "Routing and Remote Access". <br/>
Right click "DC(local)" and select "Configure and Enable Routing and Remote Access". <br/>
<img src="https://imgur.com/7AWSmtY.png" height="75%" width="75%" alt="Active Directory Steps"/>
<img src="https://imgur.com/AJnwzoe.png" height="75%" width="75%" alt="Active Directory Steps"/>
<br />
<br />
Click next. <br/>
Select the "Network address Translation (NAT)". This is how you will connect to the Internet. <br/>
Click next 2 times and then finish. <br/>
<img src="https://imgur.com/Uv6d0PJ.png" height="75%" width="75%" alt="Active Directory Steps"/>
<img src="https://imgur.com/mkJCpi0.png" height="75%" width="75%" alt="Active Directory Steps"/>
<img src="https://imgur.com/WuByNem.png" height="75%" width="75%" alt="Active Directory Steps"/>
<br />
<br />
Open Server Mananger. <br/>
Select "Add roles and features". Click next 3 times. <br/>
On Server Roles, select "DHCP Server" and then next. <br/>
<img src="https://imgur.com/cgVdQ3g.png" height="75%" width="75%" alt="Active Directory Steps"/>
<br />
<br />
You will click next 3 times. <br/>
Click Install. <br/>
In Server Manager, select "Tools" and click "DHCP". <br/>
<img src="https://imgur.com/72sowxB.png" height="75%" width="75%" alt="Active Directory Steps"/>
<br />
<br />
Right click IPv4. Select "New Scope.." and click next. <br/>
Input 172.16.0.100 for the Start IP address. <br/>
Input 172.16.0.200 for End IP address. Click next.<br/>
<img src="https://imgur.com/tvjw9c9.png" height="75%" width="75%" alt="Active Directory Steps"/>
<img src="https://imgur.com/jiWhVKC.png" height="75%" width="75%" alt="Active Directory Steps"/>
<img src="https://imgur.com/qcazFeM.png" height="75%" width="75%" alt="Active Directory Steps"/>
</p>
Click next 3 times. <br/>
Input 172.16.0.1 then click "Add". <br/>
Click next 4 times and then finish.<br/>
<img src="https://imgur.com/MRPbdRh.png" height="75%" width="75%" alt="Active Directory Steps"/>
<br />
<br/>
Minimize the DC virtual machine and open virtual box main menu. <br/>
</p>
In the menu screen click "New". <br/>
Title it "CLIENT1". <br/>
Click "Next". <br/>
<img src="https://imgur.com/mIKeAZE.png" height="75%" width="75%" alt="Active Directory Steps"/>
<br />
<br />
Choose the hardware suitable to your computer. <br/>
Click "Next". <br/>
<img src="https://imgur.com/vKZuGcP.png" height="75%" width="75%" alt="Active Directory Steps"/>
<br />
<br />
Click  "Next". <br/>
Click "Finish". <br/>
<br/>
<img src="https://imgur.com/a1nDJwz.png" height="75%" width="75%" alt="Active Directory Steps"/>
<img src="https://imgur.com/nsLONDJ.png" height="75%" width="75%" alt="Active Directory Steps"/>
<br />
<br /> 
Click on "Settings". <br/>
Under the "General" tab, do the same as you did for the DC. Change "Shared Clipboard" and "Drag'n'Drop" to Bidirectional. <br/>
<img src="https://imgur.com/EnepjKD.png" height="75%" width="75%" alt="Active Directory Steps"/>
</p>
On the "Network" tab, make Adapter 1 "Internal Network". <br/>
After this step, start the new virtual machine. <br/>
Click the drop down menu next to "DVD" and choose the Windows 10 ISO.<br/>
<img src="https://imgur.com/oPTcAbf.png" height="75%" width="75%" alt="Active Directory Steps"/>
<img src="https://imgur.com/2Izvv0a.png" height="75%" width="75%" alt="Active Directory Steps"/>
<br />
<br />
On start up click "Next". <br/>
Click "Install now". <br/>
In the bottom right choose the "I don't have a product key" option. <br/>
<img src="https://imgur.com/BIbg543.png" height="75%" width="75%" alt="Active Directory Steps"/>
<img src="https://imgur.com/fOh2YnH.png" height="75%" width="75%" alt="Active Directory Steps"/>
<br />
<br />
Choose "Windows 10 Pro". You won't be able to add it to the domain if you choose the Home version. <br/>
Accept the License Terms. Them click "Next". <br/>
Choose "Custom: Install Windows only". Then click "Next". <br/>
<img src="https://imgur.com/UPNUvlD.png" height="75%" width="75%" alt="Active Directory Steps"/>
<img src="https://imgur.com/OjE1u9O.png" height="75%" width="75%" alt="Active Directory Steps"/>
<img src="https://imgur.com/11n8ac6.png" height="75%" width="75%" alt="Active Directory Steps"/>
<img src="https://imgur.com/lOZxRNB.png" height="75%" width="75%" alt="Active Directory Steps"/>
<br />
<br />
Allow it to install. <br/>
Go through the setup. On the "Let's connect you to a netwokr." Click "I don't have internet" in the bottom left corner.<br/>
<img src="https://imgur.com/T6WkhhJ.png" height="75%" width="75%" alt="Active Directory Steps"/>
<br />
<br />
When logged into your new user, in combination press the Windows key + R to pull up the program "Run". <br/>
Type in "CMD" for command prompt. You can also just type it in the "Type here to search" bar. <br/>
In the command line type "ipconfig" to see your Ip address and default gateway. If this was setup correctly, you should <br/> see the information as its shown below. <br/>
<img src="https://imgur.com/HwRalV7" height="75%" width="75%" alt="Active Directory Steps"/>
<img src="https://imgur.com/IpwFzhM" height="75%" width="75%" alt="Active Directory Steps"/>
</p>
Now let's add it to the domain. <br/>
Right click the Windows icon in the bottom left corner of your screen and select "System". <br/>
Select "Rename this PC (advanced)". <br/>
<img src="https://imgur.com/agLuKtE.png" height="75%" width="75%" alt="Active Directory Steps"/>
<br />
<br />
Select "Change...". <br/>
Under "Computer name" type "CLIENT1". <br/>
Select the "Domain" option and type in the name of your domain. Click "OK". <br/>
<img src="https://imgur.com/O3L6w2K.png" height="75%" width="75%" alt="Active Directory Steps"/>
<img src="https://imgur.com/MjQKI7w.png" height="75%" width="75%" alt="Active Directory Steps"/>
<br />
<br />
Type in your DC admin account and password. <br/>
Restart your virtual machine. <br/>
<img src="https://imgur.com/wUqnkIf.png" height="75%" width="75%" alt="Active Directory Steps"/>
<img src="https://imgur.com/Jt6FUyB.png" height="75%" width="75%" alt="Active Directory Steps"/>
</p>
Congratulations! You have now properly setup a DC and Client virtual machine. <br/>
<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
