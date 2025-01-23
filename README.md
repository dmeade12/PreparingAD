<p align="center"><img src="https://i.imgur.com/dXRfWvO.png height="50%" width="50%" alt="image"/>
<h1>Preparing Directories Infastructure in Azure</h1>
<p>This tutorial outlines the prerequisites and setup of preparing Directories Infastructure in Azure</p>

<h3>*Environments and Technologies Used</h3>
<p>Windows 11 Pro</p>
<p>Microsoft Azure (Virtual Machines/Computer)</p>
<p>Active Directory Domain Services</p>
<p>Powershell</p>

<h3>*Operating System Used</h3>
<p>Windows 11 Pro (24H2)</p>
<p>Windows Server 2022</p>


<p>1. Create a resource Group named "Active-Directory-Lab"</p>
<p align="center"><img src="https://i.imgur.com/fRYxdUK.png> height="50%" width="50%" alt="image"/>

<p>2. Create a Virtual Network. Set the resource group to Active-Directory-Lab. Name the Virtual Network "Active-Directory-VNet" and set it to your region. Then we can review and create.</p> <p align="center"><img src="https://i.imgur.com/rK1k14D.png> height="50%" width="50%" alt="image"/>

<p>3. Create a Domain Controller VM (Windows Server 2022) named "DC-1" When creating the Virtual machine for the resource we will be using "Active-Directory-Lab". Name the VM "DC-1" and set your region as the same in your your Virtual Network. For the image set it to Windows Server 2022 Datacenter: Azure Edition - x64 Gen2. For the size choose any option with two CPU's. After that we will set a username and password. Check both licensing boxes. Lastly, click next untili you land on the Networking page.    </p> 
<p align="left "><img src="https://i.imgur.com/mEfqan0.png" height="50%" width="50%" alt="image"/> <p align=" right "><img src="https://i.imgur.com/cfVkgvL.png height="50%" width="50%" alt="image"/>
 
<p>4. Set the Virtual network to "Active-Directory-VNet then review and create. </p>
<p align="center"><img src="https://i.imgur.com/1uesmdm.png" height="50%" width="50%" alt="image"/>

<p>5. Create the directory C:\PHP</p> 

<p>6. From the “osTicket-Installation-Files” folder, unzip PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) into the “C:\PHP” folder</p>

<p>7. From the “osTicket-Installation-Files” folder, install VC_redist.x86.exe.</p>

<p>8. From the “osTicket-Installation-Files” folder, install MySQL 5.5.62 (mysql-5.5.62-win32.msi). And for the setup, select Typical Setup then Launch Configuration Wizard (after install) > Standard Configuration > Username: root & Password: root.</p>

<p>9. Open IIS as an Admin and Register PHP from within IIS (PHP Manager -> C:\PHP\php-cgi.exe)</p>
<p align="center"><img src="https://i.imgur.com/t5W1j1M.png" height="50%" width="50%" alt="image"/>

<p>10. Reload IIS (Open IIS, Stop and Start the server)</p>

<p>11. Install osTicket v1.15.8 - From the “osTicket-Installation-Files” folder, unzip “osTicket-v1.15.8.zip” and copy the “upload” folder into “c:\inetpub\wwwroot”. Within “c:\inetpub\wwwroot”, Rename “upload” to “osTicket”</p>

<p>12. Reload IIS (Open IIS, Stop and Start the server), Then Go to sites > Default > osTicketOn the right, click “Browse *:80”</p>

<p>13. Note that some extensions are not enabled, Go back to IIS, sites > Default > osTicket
<p>Double-click PHP Manager</p>
<p>Click “Enable or disable an extension”</p>
<p>Enable: php_imap.dll</p>
<p>Enable: php_intl.dll</p>
<p>Enable: php_opcache.dll</p>
<p>Refresh the osTicket site in your browser, observe the changes</p>
</p>

<p>14. Rename: ost-config.php - From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php > To: C:\inetpub\wwwroot\osTicket\include\ost-config.php</p>

<p>15. Assign Permissions: ost-config.php, Disable inheritance > Remove All. then add New Permissions > Everyone > All</p>

<p>16. Continue Setting up osTicket in the browser (click Continue). Name: Helpdesk. Default email (receives email from customers)</p>

<p>17. From the “osTicket-Installation-Files” folder, install HeidiSQL. Open Heidi SQL. Then Create a new session, Input username and password: root/root. Then connect to the session and Create a database called “osTicket”</p>
<p align="center"><img src="https://i.imgur.com/i6DxKzM.png" height="50%" width="50%" alt="image"/>

<p>18. Continue Setting up osTicket in the browser
<p>MySQL Database: osTicket</p>
<p>MySQL Username: root</p>
<p>MySQL Password: root</p>
<p>Click “Install Now!”</p>
</p>

<p>19. Congratulations, hopefully it is installed with no errors!
Browse to your help desk login page: <i> http://localhost/osTicket/scp/login.php </i></p>
<p align="center"><img src="https://i.imgur.com/u6LDs8K.png" height="50%" width="50%" alt="image"/>

<p>20. End Users osTicket URL: <i>http://localhost/osTicket/<i/> </p>
<p align="center"><img src="https://i.imgur.com/dGWkdFJ.png" height="50%" width="50%" alt="image"/>

<h4>N.B: - Clean up - Delete: C:\inetpub\wwwroot\osTicket\setup. Also set Permissions to “Read” only: C:\inetpub\wwwroot\osTicket\include\ost-config.php</h4>

