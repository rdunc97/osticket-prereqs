<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (Standard DS2, 2 vcpus/7 GiB memory)

<h2>List of Prerequisites</h2>

- Working Azure Windows 10 Virtual Machine 
- Remote Desktop Connection Program
- IIS - Internet Information Services WITH CGI (within VM) 
- PHP Manager for IIS (within VM)
- Rewrite Module (within VM)
- HeidiSQL (within VM)

<h2>Installation Steps</h2>

<p>
<img src="https://i.imgur.com/nKCFqm6.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>


<p>
🚀 Part 1: Create the Virtual Machine in Azure

1. **Go to the Azure Portal**
2. **Create a new Virtual Machine**
   - **Image**: Windows 10
   - **vCPUs**: 4
   - **Name**: `osticket-vm`
   - **Username**: `labuser`
   - **Password**: `osTicketPassword1!`
3. Click **Review + Create**, then **Create**.
---
</p>
<br />

<p>
<img src="https://i.imgur.com/wtRJxVC.png" height="40%" width="40%" alt="Connect to VM"/>
</p>
<p>
🔐 Part 2: Connect to Your VM using the public IP address

1. In Azure, go to the `osticket-vm` overview page.
2. Click **Connect > RDP**.
3. Download the `.rdp` file and log in using:
   - **Username**: `labuser`
   - **Password**: `osTicketPassword1!`
---
</p>
<br />

<p>
<img src="https://i.imgur.com/YgTkkpV.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
📁 Part 3: Setup Files in the VM

1. Download the `osTicket-Installation-Files.zip` to your **Desktop**.
2. Right-click the zip file → **Extract All...**
3. Confirm the folder name is: `osTicket-Installation-Files`.

---
</p>
<br />


<p>
<img src="https://i.imgur.com/olEEL1y.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
🌐 Part 4: Install IIS and CGI

1. Open **Control Panel > Programs > Turn Windows features on or off**
2. Check these boxes:
   - ✅ **Internet Information Services**
   - ✅ **World Wide Web Services > Application Development Features > CGI**

---
</p>
<br />

