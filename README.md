<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>Configuring On-premises Active Directory within Azure VMs Part 4</h1>
This tutorial guides the implementation of Active Directory within Microsoft Azure Virtual Machines. For this tutorial to be completed, you must finish the prerequisites first and come back to this one as it builds upon those.  <br />

<h2>Prerequisites</h2>

- [On-premises the Active Directory within Azure VMs Part 2](https://github.com/BenjaminG-Dreams/configure-ad2)

<h2>Technologies and Enviroments Used</h2>

- Microsoft Azure
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Create a Group Policy and Managing Accounts

<h2>Deployment and Set Up</h2>

![Screenshot 2025-01-31 212939](https://github.com/user-attachments/assets/a1226db2-646b-4c10-900c-7016bfeb13ae)


<p>
go to "dc-1" and press the windows key and R at the same time and put "gpmc.msc".
</p>
<br />


![Screenshot 2025-01-31 213216](https://github.com/user-attachments/assets/27fcc09d-53f6-4cfc-9d28-5a005590d85d)

<p>
Now go to forest domain and then to mydomain.com and then right-click press edit.
</p>
<br />

![Screenshot 2025-01-31 213542](https://github.com/user-attachments/assets/feacaa4c-eaf3-4e8d-b76e-504de1ab76a9)


<p>
go to computer configuration-> Windows setting-> security settings then go Account lockout threshold and put it to 5 invalid login attempts.
</p>
<br />

![Screenshot 2025-01-31 213907](https://github.com/user-attachments/assets/85988102-7447-4b87-8d77-f1468ce214d4)

![Screenshot 2025-01-31 214033](https://github.com/user-attachments/assets/1f41bc96-80dc-4d7e-a52f-6144b4f0231b)

<p>
go to "client-1"  but log in as mydomain.com\jane_admin and go to the command prompt and use "gpupdate /force" to force the policy.
</p>
<br />

![Screenshot 2025-01-31 214347](https://github.com/user-attachments/assets/d2ef564b-4609-4808-bd36-e42cef769152)

<p>
Now login  one of the 10,000 users and keep putting the incorrect password.
</p>
<br />

![Screenshot 2025-01-31 214746](https://github.com/user-attachments/assets/47bb7992-0bf7-453a-8363-1086072e0692)

![Screenshot 2025-01-31 214822](https://github.com/user-attachments/assets/45814949-cc93-4dfd-825f-4ad1e08caa72)

<p>
Now go back to "dc-1" and to one of 10,000 users that you pick and right click and then click on reset password. Now you can reset the password or just unlock the account.
</p>
<br />

![Screenshot 2025-01-31 215603](https://github.com/user-attachments/assets/d1bd5653-8cae-4a53-9c5e-e9b47b072c48)

<p>
Stay on "dc-1" and create these 4 folders: “read-access”, “write-access”, “no-access”, “IT Manager”
</p>
<br />

![Screenshot 2025-01-31 215910](https://github.com/user-attachments/assets/15f4b7e5-3772-4f73-92b2-afacee240e88)

![Screenshot 2025-01-31 220049](https://github.com/user-attachments/assets/03e89937-8d8d-4964-97e9-7d8fe5bcd729)

<p>
Now Set the following permissions (share the folder)
Folder: “read-access”, Group: “Domain Users”, Permission: “Read”
Folder: “write-access”,  Group: “Domain Users”, Permissions: “Read/Write”
Folder: “no-access”, Group: “Domain Admins”, “Permissions: “Read/Write”
For It Manager wait for that one for now.
</p>
<br />

![Screenshot 2025-01-31 220309](https://github.com/user-attachments/assets/7279913d-ce40-42ab-87a2-fdc92a069be6)

![Screenshot 2025-01-31 220354](https://github.com/user-attachments/assets/48e1a104-4800-479a-b72f-2dd032ff72b3)

<p>
Now make a new "Organizational Units" and name it "_Groups" then create a security group called “IT Manager”.

</p>
<br />

![Screenshot 2025-01-31 220521](https://github.com/user-attachments/assets/15870301-94dc-425b-950e-01654053b849)

<p>
Folder: “It Manager”, Group: “It Manager”, Permissions: “Read/Write”.
</p>
<br />

![Screenshot 2025-01-31 220702](https://github.com/user-attachments/assets/1a78c98d-7358-44b4-a97e-195f47cb0024)

![Screenshot 2025-01-31 220827](https://github.com/user-attachments/assets/eb9b3c1c-37b4-4b86-8b32-c6441e05fafc)

![Screenshot 2025-01-31 220849](https://github.com/user-attachments/assets/8abbe2cc-e3b0-4810-9e0a-88e16c10fa14)

![Screenshot 2025-01-31 221119](https://github.com/user-attachments/assets/5367d91e-556c-42e9-b7e3-0217e493c3b8)|

<p>
Try to access the folders you just created. Which folders can you access? Which folders can you create stuff in?
</p>
<br />

<h1>Thank you for looking at my tutorials for Configuring On-premises Active Directory within Azure VMs</h1>
