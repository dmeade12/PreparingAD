<p align="center"><img src="https://i.imgur.com/RPZ9Gws.png" height="50%" width="50%" alt="image"/>
<h1>osTicket Prerequisites and Installation</h1>
<p>This tutorial outlines the prerequisites and setup of preparing Directories Infastructure in Azure</p>

<h3>*Environments and Technologies Used</h3>
<p>Windows 11 Pro</p>
<p>Internet Information Services (IIS)</p>
<p>osTicket</p>

<h3>*Operating System Used</h3>
<p>Windows 11 Pro (24H2)</p>

<h3>*osTicket Installation Files</h3>
<p>https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6</p>

<h3>Download and Installation Steps</h3>
<p>1. Downloaded the osTicket file from <i><b>"https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6"</b> </i> to my windows laptop, then extracted the osTicket files to my desktop</p>
<p align="center"><img src="https://i.imgur.com/rszFcmo.png" height="50%" width="50%" alt="image"/>

<p>2. Install / Enable IIS in Windows WITH CGI - From the control panel, click on Turn windows features on and off. Then while on the Turn Windows on and off page, click on Internet Information Services(IIS), then expand the World Wide Web Services > Application Development Features, then select CGI.</p> 
<p align="center"><img src="https://i.imgur.com/8Xmv5D3.png" height="50%" width="50%" alt="image"/>

<p>3. From the “osTicket-Installation-Files” folder, install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)</p>

<p>4. From the “osTicket-Installation-Files” folder install the Rewrite Module (rewrite_amd64_en-US.msi)</p>

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

