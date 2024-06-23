<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the usage of Active Directory to create users and security groups, and assign permissions within a Virtual Machine.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)


<h2>Deployment and Configuration Steps</h2>

- Step 1
From the Server Manager dashboard, click the "Tools" dropdown in the top right.  Select "Active Directory Users and Computers."  If Server Manager is not open, you can access it through the Start menu instead.  Go to Start -> Windows Administrative Tools -> Active Directory Users and Computers.
![image](https://github.com/ScotBlair/configure-ad/assets/171102023/e2a4d5ca-4778-407b-a9ae-9f57655c127b)


- Step 2
From inside Active Directory Users and Computers, right-click on the name of your domain in the left panel (I chose MyDomain.org) and select New -> Organizational Unit.  Enter a name for the folder(s) to be created.  I created 3 folders: _ACCOUNTANTS, _IT SECURITY, and _PROGRAMMERS.


- Step 3
For each folder, I created some users:  Dave and Steve are _ACCOUNTANTS, Bob, Mark, and Rebecca (aka Becky) are part of _IT SECURITY, and Rachael, Tasha, and Xavier are _PROGRAMMERS.  In the left panel, right-click the folder you want to create a new user in, select New -> User.  Fill out the info in the pop-up screen.
![Active Directory 2](https://github.com/ScotBlair/configure-ad/assets/171102023/984c27eb-6ef9-40cc-9e21-107b5bda5f58)


- Step 4
Now we need to create a Security Group for each Organizational Unit we created so we can assign each user a membership role.  In the panel to the left, right-click the folder at the bottom named "Users", then select New -> Group.  Name your group.  In the panel on the right, the name of your new security group will appear.  Right click it and select "Properties."  Select the "Members" tab, then select "Add."  Under "Enter the object names to select," enter the name of the users you want to be part of this group.
![Members Group](https://github.com/ScotBlair/configure-ad/assets/171102023/c0476138-1b22-4a5e-8bc0-60cbce0a7efa)

- Step 5


<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
