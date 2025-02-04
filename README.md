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
<p align="center"><img src="https://i.imgur.com/EGS9GSh.png> height="50%" width="50%" alt="image"/>

<p>2. Create a Virtual Network. Set the resource group to Active-Directory-Lab. Name the Virtual Network "Active-Directory-VNet" and set it to your region. Then we can review and create.</p> <p align="center"><img src="https://i.imgur.com/rK1k14D.png> height="50%" width="50%" alt="image"/>

<p>3. Create a Domain Controller VM (Windows Server 2022) named "DC-1" When creating the Virtual machine for the resource we will be using "Active-Directory-Lab". Name the VM "DC-1" and set your region as the same in your your Virtual Network. For the image set it to Windows Server 2022 Datacenter: Azure Edition - x64 Gen2. For the size choose any option with two CPU's. After that we will set a username and password. Check both licensing boxes. Lastly, click next untili you land on the Networking page.    </p> 
<p align="left "><img src="https://i.imgur.com/mEfqan0.png" height="50%" width="50%" alt="image"/> <p align=" right "><img src="https://i.imgur.com/cfVkgvL.png height="50%" width="50%" alt="image"/>
 
<p>4. Set the Virtual network to "Active-Directory-VNet then review and create. </p>
<p align="center"><img src="https://i.imgur.com/1uesmdm.png" height="50%" width="50%" alt="image"/>

<p>5.Create another VM named "Client-1" When creating the Virtual machine for the resource we will be using "Active-Directory-Lab". Name the VM "DC-1" and set your region as the same in your your Virtual Network. For the image set it to Windows 11 Pro version 24H2 - x64 Gen2
 For the size choose any option with two CPU's. After that we will set a username and password. Check both licensing boxes. Lastly review and create.</p> <p align="center"><img src="https://i.imgur.com/bISQ2Al.png" height="50%" width="50%" alt="image"/>

<p>6.Go to Virutal Machines, set Domain Controller's NIC Private IP address to be static.To do this click on "DC-1">Go to Network Settings>Click Newtork interface / IP configuration>Go to ipconfig1>Set Private IP address settings to static and save.</p>  <p align="left"><img src="https://i.imgur.com/n3KFWkW.png" height="50%" width="50%" alt="image"/> <p align=" right "><img src="https://i.imgur.com/IlQbOxs.png height="50%" width="50%" alt="image"/>

<p>7. Go To Virtual Machines>Copy "DC-1" public adress</p> <p align="center"><img src="https://i.imgur.com/8l253TK.png  height="50%" width="50%" alt="image"/>

<p>8. For Mac user go to Microsoft Remote Desktop and for Window users go to remote desktop and sign in. <p align="center"><img src="https://i.imgur.com/pfnLsIm.png" height="50%" width="50%" alt="image"/></p> 

<p>9. Once inside the Domain Controller right click the start menu>click "run">Type "WF.MSC">Click "Windows Defender Firewall Properties">Firewall State:Turn Off and apply.(This is step is only needed for practice purposes this is not a good idea in the work enviroment) </p <p align="center"><img src="https://i.imgur.com/z71bTbv.png" height="50%" width="50%" alt="image"/></p> 

<p>10.Go back to Azure on your main device and copy the Private IP Address of "DC-1"</p>

<p>11. Go to"Client-1">Network settings>Click on your Network interface/IP configuration(Client-1286)>DNS serversCustom and paste the IP adress of "DC-1"and save.</p> </p <p align="center"><img src="https://i.imgur.com/4f99lHP.png" height="50%" width="50%" alt="image"/></p> 

<p>12. Log into "Client 1" ping DC-1's private IP address(To ensure everything was setup correctly)</p>

<p>13.Lets Ping DC-1's private IP address(To ensure everything was setup correctly)
<p>Copy the the IP Private address from "DC-1"</p>
<p>Click start or use the windows key to search Powershell</p>
<p>Type the Command Ping 10.0.0.4(You will paste your IP address after Ping) then hit enter</p> <p align="center"><img src="https://i.imgur.com/1uesmdm.png" height="50%" width="50%" alt="image"/>

<p>14. Type the command  "ipconfig /all"(The output for the DNS settings should show DC-1’s private IP Address
)</p> <p align="center"><img src="https://i.imgur.com/qgWvTDt.png" height="50%" width="50%" alt="image"/>

<p>15. Great Job, you setup your own AD Infrastructure in Azure!</p>




