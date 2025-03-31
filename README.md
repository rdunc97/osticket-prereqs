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
<img src="https://i.imgur.com/olEEL1y.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
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


<p>
</p>
<p>
## ⚙️ Part 5: Install osTicket Dependencies

### From the `osTicket-Installation-Files` folder:

1. **Install PHP Manager for IIS**
   - Run: `PHPManagerForIIS_V1.5.0.msi`

2. **Install IIS Rewrite Module**
   - Run: `rewrite_amd64_en-US.msi`

3. **Create folder `C:\\PHP`**

4. **Extract PHP 7.3.8** to `C:\\PHP`
   - File: `php-7.3.8-nts-Win32-VC15-x86.zip`

5. **Install Visual C++ Redistributable**
   - Run: `VC_redist.x86.exe`

6. **Install MySQL 5.5.62**
   - Run: `mysql-5.5.62-win32.msi`
   - Choose: **Typical Setup**
   - After install: **Launch Configuration Wizard**
   - Choose: **Standard Configuration**
   - Username: `root`
   - Password: `root`

---
</p>
<br />





<p>
<img src="https://i.imgur.com/t7f6tcR.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
</p>
<p>
🌐 Part 6: Configure IIS and PHP

1. Open **IIS Manager as Administrator**
2. In **PHP Manager**, register PHP:
   - Path: `C:\\PHP\\php-cgi.exe`
3. Restart IIS:
   - Click on the server name → **Stop** and **Start**

---
</p>
<br />



<p>
<img src="https://i.imgur.com/K9kaHNn.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
</p>
<p>
📥 Part 7: Install osTicket Files

1. Extract `osTicket-v1.15.8.zip`
2. Copy the **upload** folder into:
   - `C:\\inetpub\\wwwroot`
3. Rename the folder:
   - From: `upload`
   - To: `osTicket`
4. Restart IIS again.

---
</p>
<br />



<p>
<img src="https://i.imgur.com/KtNipzf.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
<p> 📸 *Note: your page may look different, mine was already installed* </p>
</p>
<p>
🌍 Part 8: Launch osTicket in Browser

1. In IIS Manager, go to:
   - `Sites > Default Web Site > osTicket`
2. On the right, click **Browse *:80**
3. A setup page should appear. It might show missing extensions.
---
</p>
<br />



<p>
<img src="https://i.imgur.com/5JrUOaK.png" height="65%" width="65%" alt="Disk Sanitization Steps"/>
</p>
<p>
⚙️ Part 9: Enable Required PHP Extensions

1. In IIS → Sites → Default → osTicket
2. Double-click **PHP Manager**
3. Click **Enable or disable an extension**
4. Enable the following:
   - ✅ `php_imap.dll`
   - ✅ `php_intl.dll`
   - ✅ `php_opcache.dll`
5. Refresh the browser.
---
</p>
<br />



<p>
<img src="https://i.imgur.com/TjaFCC7.png" height="65%" width="65%" alt="Disk Sanitization Steps"/>
</p>
<p>
🛠️ Part 10: Rename Config File

1. Go to:  
   - `C:\\inetpub\\wwwroot\\osTicket\\include`
2. Rename:
   - From: `ost-sampleconfig.php`
   - To: `ost-config.php`

3. Set permissions:
   - Right-click the file → **Properties > Security**
   - Click **Advanced**
   - Disable inheritance and remove all
   - Add permission:
     - User: `Everyone`
     - Allow: `Full control`
---
</p>
<br />



<p>
</p>
<p>
✍️ Part 11: Complete osTicket Setup in Browser

1. Go back to your browser.
2. Fill in the setup:
   - Helpdesk Name: *Your Choice*
   - Default email: *Your Choice*

---
</p>
<br />

