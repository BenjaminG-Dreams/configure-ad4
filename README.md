<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>Configuring On-premises Active Directory within Azure VMs Part 3</h1>
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

- Create additional users and attempt to log into client-1 with one of the users

<h2>Deployment and Set Up</h2>

![Screenshot 2025-01-31 211435](https://github.com/user-attachments/assets/2b3b3017-c216-4e7b-b919-623c22ba0ca8)

![Screenshot 2025-01-31 211506](https://github.com/user-attachments/assets/a81b0dce-639a-4ea9-a083-5dd0a16bbee8)




<p>
While in DC-1, open "Windows Powershell ISE (x86)" as admin.
</p>
<br />

![Screenshot 2025-01-31 211506](https://github.com/user-attachments/assets/a81b0dce-639a-4ea9-a083-5dd0a16bbee8)

![Screenshot 2025-01-31 211654](https://github.com/user-attachments/assets/b74ba8f2-9b08-4f69-834f-5593ef0c99b6)

![Screenshot 2025-01-31 211740](https://github.com/user-attachments/assets/0b31f1e1-cb3d-46b3-865c-75d95c758045)

![Screenshot 2025-01-31 212214](https://github.com/user-attachments/assets/15e51339-7e54-4f72-8200-67f167ad2293)

<p>
Now create 10,000 users with a randomly generated names by copying the powershell script linked below. To do this we will create a new script by pressing the button at the top left > paste script > and then hit the green run script button.

- [Script](https://github.com/joshmadakor1/AD_PS/blob/master/Generate-Names-Create-Users.ps1)

![Screenshot 2025-01-31 212427](https://github.com/user-attachments/assets/3633626d-8b6a-4232-8e38-784f1dfc572e)

<p>
Finally, log in with one of the 10,000 users with a randomly generated names and with 
</p>
<br />

<h1>Stay Tuned for On-premises Active Directory within Azure VMs Part 4</h1>
