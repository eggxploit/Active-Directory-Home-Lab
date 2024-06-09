<h1>Active Directory Home Lab</h1>

 ### [YouTube Demonstration](https://youtu.be/6O7Dru6jQe4)

<h2>Description</h2>
In this lab, we'll learn how to set up an Active Directory home lab using Oracle VirtualBox. This will help you understand Active Directory and Windows networking. Take your time with the tutorial to grasp each step. Write down any questions you have about the process and try to build it on your own without always relying on the tutorial.
<br />

<h2>Network Topology</h2>
<p align="center">
<img src="https://i.imgur.com/xgW6zsm.jpeg" alt="Network Topology"/>

<br />
 
<h2>Utilities Used </h2>

- <b>PowerShell</b>

<h2>Environments Used </h2>

- <b><a href="https://www.microsoft.com/en-us/software-download/windows10">Windows 10</a></b>
- <b><a href="https://www.microsoft.com/en-us/evalcenter/download-windows-server-2019">Server 2019</a></b>
- <b><a href="https://www.virtualbox.org/wiki/Downloads">VirtualBox</a><b>

<h2>Program Walk-Through:</h2>

<p align="center">
  Download VirtualBox, Windows 10 ISO, and Server 2019 ISO<br />
  <img src="https://i.imgur.com/9xKIz3y.png" height="80%" width="80%" alt="Download VirtualBox"/><br />
  <em>Make sure to choose your appropriate OS and the Extension Pack</em><br /><br /><br />
  <img src="https://i.imgur.com/qk7b14I.png" height="80%" width="80%" alt="Download Windows Server 2019 ISO"/><br /><br /><br />
  <img src="https://i.imgur.com/cQYHfMG.png" height="80%" width="80%" alt="Download Windows 10 ISO"/><br /><br /><br />
  <img src="https://i.imgur.com/QyViHym.png" height="80%" width="80%" alt="Creating DC 1"/><br />
  <em>You can change the name to anything you want. I chose DC to make it simple. Be sure to use the Server 2019 ISO that we've downloaded previously and check the box for "Skip Unattended Installation".</em><br /><br />  
  <br />
  <img src="https://i.imgur.com/cCoORaL.png" height="80%" width="80%" alt="Creating DC 2"/><br />
  <em>Assuming you have at least 8 GB of RAM, set the RAM to 2 GB. You can also leave the CPUs as 1 and it will still work. Feel free to use more if you have more resources. It will make the processes run faster.</em><br /><br />
  <br />
  <img src="https://i.imgur.com/3n7K4hF.png" height="80%" width="80%" alt="Creating DC 3"/><br />
  <em>50 GB is more than enough but if you don't have a lot of resources then 20 GB will work just as fine.</em><br /><br />  
  <br />
  <img src="https://i.imgur.com/HvTVJFN.png" height="80%" width="80%" alt="Creating DC 4"/><br />
  <em>Look over to double-check if it's correct and click Finish.</em><br /><br />
  <br />
  <img src="https://i.imgur.com/jEV5vYU.png" height="80%" width="80%" alt="Creating DC 5"/><br />
  <em>Click on Settings > General > Advanced and change "Shared Clipboard" and "Drag'n'Drop" to Bidirectional. This will make it easier to copy and paste to and from the host PC to the VM.</em><br /><br /><br />
  <img src="https://i.imgur.com/6guLwxP.png" height="80%" width="80%" alt="Creating NAT"/><br />
  <em>Ensure that you have NAT enabled.</em><br /><br /><br />
  <img src="https://i.imgur.com/E4AhDlN.png" height="80%" width="80%" alt="Creating Internal Network"/><br />
  <em>Click on the "Adapter 2" tab, check the box for "Enable Network Adapter", and use the drop-down menu to change to "Internal Network".</em><br /><br /><br />
  <img src="https://i.imgur.com/uvrFjhJ.png" height="80%" width="80%" alt="Powering on DC"><br />
  <em>VM is configured but empty so power on your VM by clicking "Start" or double-clicking on it. Then click on "Install".</em><br /><br />
  <br />
  <img src="https://i.imgur.com/JlQSFR7.png" height="80%" width="80%" alt="Setting up Server 2019"><br />
  <em>Make sure to choose Standard or Datacenter "Desktop Experience" so that you have a GUI to use, or else you will have a command line interface.</em><br /><br /><br />
  <img src="https://i.imgur.com/c3LJZpn.png" height="80%" width="80%" alt="Custom install Windows 2019"><br />
  <em>Click on "Custom" so we can start from scratch and format the hard drive.</em><br /><br /><br />
  <img src="https://i.imgur.com/Zb4ammI.png" height="80%" width="80%" alt="Windows Install Destination"><br />
  <em>Click on the unallocated space that we set up earlier and click Next. After you click "Next", allow the VM to boot up again and do not touch anything until you reach this "Customize settings" screen. There will be a screen that pops up to ask you to boot from CD or DVD, do not press anything and allow it to pass through</em><br /><br /><br />
  <img src="https://i.imgur.com/MINGD63.png" heigfht="80%" width="80%" alt="Post Server Setup"><br />
  <em>You can set your password to something simple since this is a lab environment. I have set it up as "Password1" for simplicity.</em><br /><br /><br />
  <img src="https://i.imgur.com/KIpw4lX.png" height ="80%" width="80%" alt="Signing into Server 2019"><br />
  <em>Sign in with the password you created earlier. (I made it Password1)</em><br /><br /><br />
  <img src="https://i.imgur.com/7QGF55h.png" height="80%" width="80%" alt="Insert Guest Additions"><br />
  <em>Insert the Guest Additions from the "Devices" tab.</em><br /> <br /><br />
  <img src="https://i.imgur.com/M7dHuK9.png" height="80%" width="80%" alt="Picture"><br />
  <em>Open File Explorer navigate to This PC> VirtualBox Guest Additons> VBoxWindowsAdditions-amd64 and run the application.</em><br /> <br /><br />
  <img src="https://i.imgur.com/HzFzWo2.png" height="80%" width="80%" alt="Picture"><br />
  <em>Fully install Guest Additions, click "manually reboot later" and finish. You may experience some errors if you allow it to reboot so we will manually shut it down and reboot the VM. </em><br /> <br /><br />
  <img src="https://i.imgur.com/75UTGBv.png" height="80%" width="80%" alt="Picture"><br />
  <em>Reboot the VM from VirtualBox but clicking on start or double-clicking the VM. Log back into the account again. You should be able to re-adjust your window size now which will make things much easier down the line.</em><br /> <br /><br />
  <img src="https://i.imgur.com/iS5UyMi.png" height="80%" width="80%" alt="Picture"><br />
  <em>Open Network Settings and navigate to "Change adapter options". We are going to rename the network connections so that it is easier to identify later on.</em><br /> <br /><br />
  <img src="https://i.imgur.com/aGAghEE.png" height="80%" width="80%" alt="Picture"><br />
  <em>Choose one to the network, right-click and click on "status" and then "details". This window should open up and if you see something like "10.0.2.15", this indicates that this is a private IP address just like your PC. This is the network that is connected to the internet.</em><br /> <br /><br />
 <img src="https://i.imgur.com/mcJtRfb.png" height="80%" width="80%" alt="Picture"><br />
 <em>We just renamed our internet facing network "_INTERNET_".</em><br /> <br /><br />
 <img src="https://i.imgur.com/IfBm2bz.png" height="80%" width="80%" alt="Picture"><br />
 <em>Although we know that the other network is the internal network, this is a good way to see how the Automatic Private IP Addressing (APIPA) works. You can see that the IP address is between 169.254.0.1 to 169.254.255.254 range which is strictly for APIPA.</em><br /> <br /><br />
 <img src="https://i.imgur.com/8Jg74bU.png" height="80%" width="80%" alt="Picture"><br />
 <em>I have changed the internal network to "X_Internal_X" to make it easier to spot since Internet and Internal look very similar.</em><br /> <br /><br />
 <img src="https://i.imgur.com/21zgUDk.png" height="80%" width="80%" alt="Picture"><br />
 <em>To set up the IP address for the X_Internal_X network, right-click the network and go to Properties. Double-click on IPV4 and another window should pop up. I assigned the IP address to 172.16.0.1 with a subnet mask of 255.255.255.0 and the DNS server as itself. You can also use 127.0.0.1 for the input for DNS server. 127.0.0.1 is a loopback address so it will essentially be the same as referring to itself.</em><br /> <br /><br />
 <img src="https://i.imgur.com/YYsgCXT.png" height="80%" width="80%" alt="Picture"><br />
 <em>After applying and confirming the change, we will rename our PC to DC for convenience. Right-click the start menu and click on system. Click on "Rename this PC" I chose to go with DC short for Domain Controller however, it is up to you if you want to rename it something else. Finally, restart the PC.</em><br /> <br /><br />
 <img src="https://i.imgur.com/BPxwnMM.png" height="80%" width="80%" alt="Picture"><br />
 <em>We will begin adding our Active Directory Domain Services and creating a Domain. In the Server Manager Dashboard, click on add Roles and Features.</em><br /> <br /><br />
 <img src="https://i.imgur.com/bGYPfdq.png" height="80%" width="80%" alt="Picture"><br />
 <em>Click on Role-based or feture-based installation and click next.</em><br /> <br /><br />
 <img src="https://i.imgur.com/EdHSn2f.png" height="80%" width="80%" alt="Picture"><br />
 <em>You should only have one server so select the server and click next.</em><br /> <br /><br />
 <img src="https://i.imgur.com/qtRwxoT.png" height="80%" width="80%" alt="Picture"><br />
 <em>Be sure to select the correct one which is domain services.</em><br /> <br /><br />
 <img src="https://i.imgur.com/CMosxFx.png" height="80%" width="80%" alt="Picture"><br />
 <em>Leave everything as is in Features.</em><br /> <br /><br />
 <img src="https://i.imgur.com/dcppo80.png" height="80%" width="80%" alt="Picture"><br />
 <em>Confirm everything is correct and click Install.</em><br /> <br /><br />
 <img src="https://i.imgur.com/Vw4Z7zJ.png" height="80%" width="80%" alt="Picture"><br />
 <em>After AD DS has been installed, we must perform our post-deployment configuration and promote the server to a domain controller. Click on "Promote this server to a domain controller".</em><br /> <br /><br />
 <img src="https://i.imgur.com/TJP0dbI.png" height="80%" width="80%" alt="Picture"><br />
 <em>Click on "Add a new forest" and change the domain name to "mydomain.com" and click next.</em><br /> <br /><br />
 <img src="https://i.imgur.com/5WueIqI.png" height="80%" width="80%" alt="Picture"><br />
 <em>Put in a the same password as before to make it simple. You must put a password in to move to the next step but we won't need to use this. Click next on the next tab without checking the box for "Create DNS delegation".</em><br /> <br /><br />
 <img src="https://i.imgur.com/lrA2zt9.png" height="80%" width="80%" alt="Picture"><br />
 <em>Click next on everything without changing any of the settings and then click install. It will automatically restart after.</em><br /> <br /><br />
 <img src="https://i.imgur.com/pUVliV9.png" height="80%" width="80%" alt="Picture"><br />
 <em>This is a confirmation that your domain was created correctly and you can now see MYDOMAIN\Administrator.</em><br /> <br /><br />
 <img src="https://i.imgur.com/FAK0fZF.png" height="80%" width="80%" alt="Picture"><br />
 <em>Once you are logged in, Start menu> Windows Administrative Tools> Active Directory Users and Computers.</em><br /> <br /><br />
 <img src="https://i.imgur.com/5RCfGRp.png" height="80%" width="80%" alt="Picture"><br />
 <em>Creating OU for Admin account.</em><br /> <br /><br />
 <img src="https://i.imgur.com/sk5q2AJ.png" height="80%" width="80%" alt="Picture"><br />
 <em>Name your OU and to make things run smoother, uncheck the box "Protect container from accidental deletion".</em><br /> <br /><br />
 <img src="https://i.imgur.com/6WWbB1i.png" height="80%" width="80%" alt="Picture"><br />
 <em>Right-click _ADMINS> New> User. I used my own name and for my user, I used the standard name that businesses use. (a-(first_initial)(last_name)) </em><br /> <br /><br />
 <img src="https://i.imgur.com/Fr7UloM.png" height="80%" width="80%" alt="Picture"><br />
 <em>I used the same password and checked "Password never expires" to not give myself a headache.</em><br /> <br /><br />
 <img src="https://i.imgur.com/yDnHl0D.png" height="80%" width="80%" alt="Picture"><br />
 <em>Now that we created our user, we need to give it admin rights. Right-click the newly created user and open properties. Click on "Member of" tab. Type in Domain Admins and click on "check names" so that it will autocorrect the object. Click OK, Apply, and OK.</em><br /> <br /><br />
 <img src="https://i.imgur.com/88dVq32.png" height="80%" width="80%" alt="Picture"><br />
 <em>Sign out and log into your newly created user. Click on "Other user" in the bottom left corner and log in with the credentials that you created.</em><br /> <br /><br />
 <img src="https://i.imgur.com/rTEWuSI.png" height="80%" width="80%" alt="Picture"><br />
 <em>We are going to set up the NAT. Click on "add roles and features" and continue through the process as we did before. Once we get to the Server Roles tab, check the "Remote Access" tab. Click next until you reach "Role Services".</em><br /> <br /><br />
 <img src="https://i.imgur.com/IKaHyrW.png" height="80%" width="80%" alt="Picture"><br />
 <em>Check the routing box and accept. It will automatically check the DirectAccess and VPN (RAS). Keep clicking Next and install.</em><br /> <br /><br />
 <img src="https://i.imgur.com/sQ4OlZx.png" height="80%" width="80%" alt="Picture"><br />
 <em>Head to the tools tab and open "Routing and Remote Access"</em><br /> <br /><br />
 <img src="https://i.imgur.com/B9f8O26.png" height="80%" width="80%" alt="Picture"><br />
 <em> Right-click your Domain Controller and click on "Configure and Enable Routing and Remote Acces"</em><br /><br /><br />
 <img src="https://i.imgur.com/050IHJf.png" height="80%" width="80%" alt="Picture"><br />
 <em>Make sure to change it to NAT and click next.</em><br /> <br /><br />
 <img src="https://i.imgur.com/Er6i6Mn.png" height="80%" width="80%" alt="Picture"><br />
 <em>Click the top bullet and click on the network that is connected to the internet. If you don't see it show up, you may need to close the window and redo the process. Reopen the tools menu and go back to Routing and Remote Access and it should show up. Click Finish.</em><br /> <br /><br />
 <img src="https://i.imgur.com/o8N0hST.png" height="80%" width="80%" alt="Picture"><br />
 <em>Notice the up arrow to the left of the Domain Controller. This indicates that the NAT is configured.</em><br /> <br /><br />
 <img src="https://i.imgur.com/ci3NESp.png" height="80%" width="80%" alt="Picture"><br />
 <em>We're going to set up the DHCP. Open up Add Roles and Features and click next until you reach Server Roles. Check the box DHCP and click on add features. Then click next and install.</em><br /> <br /><br />
 <img src="https://i.imgur.com/TkbBKcK.png" height="80%" width="80%" alt="Picture"><br />
 <em>Go to Tools> DHCP to open up the DHCP window.</em><br /> <br /><br />
 <img src="https://i.imgur.com/6U55pNw.png" height="80%" width="80%" alt="Picture"><br />
 <em>Expand the drop-down and right-click on IPv4 and click on New Scope.</em><br /> <br /><br />
 <img src="https://i.imgur.com/SHe64r0.png" height="80%" width="80%" alt="Picture"><br />
 <em>Naming our scope the name of the range of the IP addresses.</em><br /> <br /><br />
 <img src="https://i.imgur.com/k32qKZK.png" height="80%" width="80%" alt="Picture"><br />
 <em>Fill in the range in the blank space and increase the length to 24 to achieve our specified subnet mask. Skip the exclusions on the next page. </em><br /> <br /><br />
 <img src="https://i.imgur.com/jaO63IC.png" height="80%" width="80%" alt="Picture"><br />
 <em>Make sure to click on Yes to configure the DHCP options now.</em><br /><br /><br />
 <img src="https://i.imgur.com/gPie7bZ.png" height="80%" width="80%" alt="Picture"><br />
 <em>We are assigning an IP address to the default gateway. The DC needs to be able to forward traffic from the clients to the internet. The clients will be using the internal NIC in the Domain Controller as their default gateway, therefore, we will add 172.16.0.1 as the default gateway.</em><br /><br /><br />
 <img src="https://i.imgur.com/nlVcpbB.png" height="80%" width="80%" alt="Picture"><br />
 <em>This part is asking what we would like to use for our DNS server. When we installed Active Directory on the DC, it automatically installed DNS. Because of that, we will leave the DC as our DNS server too. If we don't do this, then we won't be able to join the domain. Leave this page as is and click next. Skip through the WINS Servers, it is not required. Click yes to activate the scope and then click finish.</em><br /><br /><br />
 <img src="https://i.imgur.com/uX0ZfdQ.png" height="80%" width="80%" alt="Picture"><br />
 <em>As you can see, the icons next to IPv4 and IPv6 have a green check mark. Right-click on your DC(dc.mydomain.com) and click authorize. Right-click again and click refresh. You now have a functional DNS.</em><br /><br /><br />
 <img src="https://i.imgur.com/4cJo0qa.png" height="80%" width="80%" alt="Picture"><br />
 <em>We are going to make a configuration to let us browse the Internet through the DC.(Not recommended for a production environment but for lab purposes we will.). Click "Configure this local server", Click on "On" near the IE Enhanced Security Configurations, and turn off security for both Administrators and Users.</em><br /><br /><br />
 <img src="https://i.imgur.com/s4B1Fnz.png" height="80%" width="80%" alt="Picture"><br />
 <em>Open up IE and paste "https://github.com/eggietama/ActiveDirectoryLab/raw/main/AD_PS-master.zip" into the URL to save the file onto the VM. (Thank you to Josh Madakor for providing the PowerShell script for this project.) Click save as and save it on your desktop for easy access. Extract the folder onto the desktop.</em><br /><br /><br />
 <img src="https://i.imgur.com/8rYvN0y.png" height="80%" width="80%" alt="Picture"><br />
 <em>Open up the folder that we've extracted and open up the file called "names". Add your name to the top of the list and save the file.</em><br /><br /><br />
 <img src="https://i.imgur.com/XQUqcHy.png" height="80%" width="80%" alt="Picture"><br />
 <em>Click on the Start Menu> Windows PowerShell> Windows PowerShell ISE. Right-click and run as Administrator. Once opened, click on file> open. Navigate to the folder with the script and select "1_CREATE_USERS". Click open. </em><br /><br /><br />
 <img src="https://i.imgur.com/6DDyppP.png" height="80%" width="80%" alt="Picture"><br />
 <em>If we ran the script as is, the preconfigured settings would not allow it to run because the script is not digitally signed. To get around this, type in the bottom window, "Set-ExecutionPolicy Unrestricted" and press enter. Click yes to all.</em><br /><br /><br />
 <img src="https://i.imgur.com/b3ABPB4.png" height="80%" width="80%" alt="Picture"><br />
 <em>This is just an explanation of the script so if you are not interested then move on to the next slide. Line 2 sets "Password1" as the variable "PASSWORD_FOR_USERS". The content from the file "names.txt"(the file where we put our own name in), is set as the variable "USER_FIRST_LAST_LIST". Line 6 converts the plain text password "Password1" into a secure string. Line 7 New-ADOrganizationalUnit creates a new organizational unit named _USERS in Active Directory and sets it to not be protected from accidental deletion.</em><br /><br /><br />
 <img src="https://i.imgur.com/Z7Uwj2E.png" height="80%" width="80%" alt="Picture"><br />
 <em>Line 9 iterates over each name in $USER_FIRST_LAST_LIST. Line 10 and 11 splits each name into first and last and converts to lowercase. Line 12 creates a username from the first letter of the first name and the full last name, also in lowercase. Line 13 prints the created username to the console with specific colors.Lines 15-23 creates a new user in AD with all the information gathered previously.</em><br /><br /><br />
 <img src="https://i.imgur.com/6aYj7zc.png" height="80%" width="80%" alt="Picture"><br />
 <em>The PowerShell script will only work if we are in the same directory with the file "names.txt". Change directory to the folder by using an absolute path, cd C:\Users\(your account name)\Desktop\AD_PS-master. Click on Play on the top menu bar and click on run once. You may notice some errors which are some names that have the same last name and first initial, you can ignore it.</em><br /><br /><br />
 <img src="https://i.imgur.com/K8qMrJ7.png" height="80%" width="80%" alt="Picture"><br />
 <em>You can navigate to your AD and you'll see the newly created OU "_USERS" and if you expand it, you will see the all of the users that the script had just created. As of right now, we are done with the DC so you can minimize the VM. We will begin creating a new VM to act as a user.</em><br /><br /><br />
 <img src="https://i.imgur.com/g0JvqOx.png" height="80%" width="80%" alt="Picture"><br />
 <em>The same way we created the VM for the DC, navigate back to VirtualBox and click on "New". Rename to "CLIENT1" and click next.</em><br /><br /><br />
 <img src="https://i.imgur.com/CSJtdX7.png" height="80%" width="80%" alt="Picture"><br />
 <em>Same as the DC, if you have extra resources to give this VM, you can change it. It will still work with 2 GB of RAM and 1 CPU. Create a virtual disk with the standard storage VirtualBox provides and click finish. </em><br /><br /><br />
 <img src="https://i.imgur.com/RZONzr0.png" height="80%" width="80%" alt="Picture"><br />
 <em>Open the settings of the new VM that you created, General> Advanced> change "Shared Clipboard" and "Drag'n'Drop" to "Bidirectional". Go to the Network tab and change the network to "Internal Network". Power on the VM.</em><br /><br /><br />
 <img src="https://i.imgur.com/jGiOlF4.png" height="80%" width="80%" alt="Picture"><br />
 <em>It will prompt you to select the ISO file. Browse to add the ISO file for Windows 10 and click "mount and retry boot". Click on Install Windows and "I don't have a product key"</em><br /><br /><br />
 <img src="https://i.imgur.com/YwWNS10.png" height="80%" width="80%" alt="Picture"><br />
 <em>Make sure to choose Windows 10 Pro. The "Home" version cannot connect to a domain. Install Windows. Continue to set up the Windows installation as usual.</em><br /><br /><br />
 <img src="https://i.imgur.com/ww9szJq.png" height="80%" width="80%" alt="Picture"><br />
 <em>If it ask for personal use of organization, choose home. It will prompt you to create a Microsoft account, you can choose an offline account. Then, limited experience. It will ask you to name the PC. I named it "user" and left the password blank. If you have the choice to skip a setup process, do so. </em><br /><br /><br />
 <img src="https://i.imgur.com/XOHQNeK.png" height="80%" width="80%" alt="Picture"><br />
 <em>We are going to do two things here: Rename the PC and connect to the domain. Right-click the start menu and open up system. Instead of clicking on Rename this PC, Click on Rename this PC (advanced). Click on "Change..." and rename the PC to CLIENT1 and add "mydomain.com" to "Member of Domain". Click OK.</em><br /><br /><br />
 <img src="https://i.imgur.com/Fvti0i8.png" height="80%" width="80%" alt="Picture"><br />
 <em>Once it prompts you to enter a name and password, you can put in the admin account that you've made previously and click ok. It will ask you to restart, click on restart now.</em><br /><br /><br />
 <img src="https://i.imgur.com/dyVrmw9.png" height="80%" width="80%" alt="Picture"><br />
 <em>Since we connected to the domain that we created, we can check for the IP address lease on DHCP. One the DC VM, navigate to DHCP on the Server Manager, expand the scope, and click on Address Leases. You should see that CLIENT1 was assigned an IP Address from DHCP. </em><br /><br /><br />
 <img src="https://i.imgur.com/ZoeCq1m.png" height="80%" width="80%" alt="Picture"><br />
 <em>You can also navigate to AD Users and Computers to see the PC on the domain. This shows the Vm that we created to be a part od the domain and hypothetically, if we were to delete this PC from this window, CLIENT1 will no longer be able to connect to the domain and use one of the logins we created previously.</em><br /><br /><br />
 <img src="https://i.imgur.com/ZlI14gs.png" height="80%" width="80%" alt="Picture"><br />
 <em>Go back to the CLIENT1. We will now try to log in using the credentials we created from the PowerShell script. I logged in using the one from my name.</em><br /><br /><br />
 <img src="https://i.imgur.com/QaAKWGD.png" height="80%" width="80%" alt="Picture"><br />
 <em>Now that we logged in, we can check who we are by going to the command prompt and type in "whoami". You'll see that the user is connect to "mydomain" and it's username.</em><br /><br /><br />
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
