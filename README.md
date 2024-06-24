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

- Step 1<br />
From the Server Manager dashboard, click the "Tools" dropdown in the top right.  Select "Active Directory Users and Computers."  If Server Manager is not open, you can access it through the Start menu instead.  Go to Start -> Windows Administrative Tools -> Active Directory Users and Computers.

![image](https://github.com/ScotBlair/configure-ad/assets/171102023/e2a4d5ca-4778-407b-a9ae-9f57655c127b)


- Step 2<br />
From inside Active Directory Users and Computers, right-click on the name of your domain in the left panel (I chose MyDomain.org) and select New -> Organizational Unit.  Enter a name for the Organizational Unit(s) to be created; they will look like a folder.  I created 3 Organizational Units: _ACCOUNTANTS, _IT SECURITY, and _PROGRAMMERS.


- Step 3<br />
For each folder, I created some users:  Dave and Steve are _ACCOUNTANTS.  Bob, Mark, and Rebecca (aka Becky) are part of _IT SECURITY.  And Rachael, Tasha, and Xavier are _PROGRAMMERS.  In the left panel, right-click the folder you want to create a new user in, select New -> User.  Fill out the info in the pop-up screen.

![Active Directory 2](https://github.com/ScotBlair/configure-ad/assets/171102023/984c27eb-6ef9-40cc-9e21-107b5bda5f58)


- Step 4<br />
Now we need to create a Security Group for each Organizational Unit we created so we can assign each user a membership role.  In the panel to the left, right-click the folder at the bottom named "Users", then select New -> Group.  Name your group.  In the panel on the right, the name of your new security group will appear.  Right-click it and select "Properties."  Select the "Members" tab, then select "Add."  Under "Enter the object names to select," enter the name of the users you want to be part of this group.

![Active Directory 1](https://github.com/ScotBlair/configure-ad/assets/171102023/60ac2099-43fb-4e41-9897-da0dc1ceba71)

![Members Group](https://github.com/ScotBlair/configure-ad/assets/171102023/c0476138-1b22-4a5e-8bc0-60cbce0a7efa)


- Step 5<br />
Now that our users are part of a group, it's time to give them permissions!  On the local C:\ drive, I created 3 folders, each one corresponding to the names of the Organizational Units created earlier, and in each folder, a sub folder for each user.  Right-click each folder and select "Properties."  Select the "Sharing" tab, then select "Share."  In the drop-down box to the left of the word "Add," enter the security group name we created.  For example, if we are accessing the properties of the _ACCOUNTANTS folder, then we would enter "Accountants."  When finished with each one, select "Share," then close the properties tab.

![Shared Files](https://github.com/ScotBlair/configure-ad/assets/171102023/9ce4f66a-3460-445e-92d6-6420f6919649)


- Step 6<br />
On the client pc running Windows 10, I logged into the user Xavier, who is part of the PROGRAMMERS group.  I tried to access the _ACCOUNTANTS folder by opening "File Explorer" on the task bar, selecting "Network" in the left panel, then in the main window selecting WIN-A7PMC2B3E0E -> _ACCOUNTANTS.  As Xavier, I naturally did not have permission to do so and was hit with an error message.  However, when I tried to access the _PROGRAMMERS folder, I was unrestricted.<br />
*Note: WIN-A7PMC2B3E0E is the name of the server pc.

![Sharing 1](https://github.com/ScotBlair/configure-ad/assets/171102023/12d2285d-6c57-4b68-b435-6664d59991e9)

![Sharing 2](https://github.com/ScotBlair/configure-ad/assets/171102023/be0d034b-d6f5-478f-ae8e-d9507363580a)



