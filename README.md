<h1>SIEM-Home-Lab</h1>
<h2>Description</h2>
In this lab, I set up a SIEM (Azure Sentinel) and connected it to an active VM (acting as my honeypot). Using this, I was able to monitor live attacks (Brute Forcing RDP) globally. I used a custom PowerShell script to search for the attackers' geographic location and created an Azure Sentinel map using this data.
<br />


<h2>Languages and Utilities Used</h2>

- <b>PowerShell</b> 
- <b>Microsoft Azure</b>
- <b>Microsoft Sentinel</b>

<h2>Environments Used </h2>

- <b>Windows 11</b> 

<h2>Lab walk-through</h2>

<p align="center">
Creating a Virtual Machine and settings: <br/>
<img src="https://imgur.com/bEJMMdI.png" height="80%" width="80%" alt="SIEM Lab"/>
<br />
<br />
Configuring the firewall to be extremely open, making the virtual machine easily discoverable:  <br/>
<img src="https://i.imgur.com/ZfAMHjJ.png" height="80%" width="80%" alt="SIEM Lab"/>
<br />
<br />
Creating a Log Analytics Workspace: <br/>
<img src="https://i.imgur.com/dARmFUo.png" height="80%" width="80%" alt="SIEM Lab"/>
<br />
<br />
Going to Microsoft Defender for the Cloud to enable the ability to gather logs from the VM into the LAW and then connecting it all together:  <br/>
<img src="https://i.imgur.com/nbiEIXN.png" height="80%" width="80%" alt="SIEM Lab"/>
<br />
<br />
Creating and then adding Microsoft Sentinel to the LAW:  <br/>
<img src="https://i.imgur.com/VKGRqkg.png" height="80%" width="80%" alt="SIEM Lab"/>
<br />
<br />
Turning Microsoft Defender Firewall off (in VM):  <br/>
<img src="https://i.imgur.com/vOzCPzy.png" height="80%" width="80%" alt="SIEM Lab"/>
<br />
<br />
Going to the GeoLocation API and getting my own API key (after creating an account) on the VM:  <br/>
<img src="https://i.imgur.com/pC37Jk5.png" height="80%" width="80%" alt="SIEM Lab"/>
<br />
<br />
Downloading the PowerShell script from GitHub (with permission), inserting my own API key into the script, and then running it on Microsoft PowerShell ISE to get attackers' geographical data:  <br/>
<img src="https://i.imgur.com/bqhLAHK.png" height="80%" width="80%" alt="SIEM Lab"/>
<br />
<br />
Going to the failed RDP log-in geographic data log program file on the VM and copying the contents inside of it: <br/>
<img src="https://i.imgur.com/AyB7bbe.png" height="80%" width="80%" alt="SIEM Lab"/>
<br />
<br />
Pasting the logs from the program file into Notepad, then saving it (as .log):  <br/>
<img src="https://i.imgur.com/YFohPno.png" height="80%" width="80%" alt="SIEM Lab"/>
<br />
<br />
Creating a custom log in LAW by using the file created from Notepad, then running it in Logs:  <br/>
<img src="https://i.imgur.com/nksMhYH.png" height="80%" width="80%" alt="SIEM Lab"/>
<br />
<br />
Extracting the Geographical data by creating a custom query (with the log created):  <br/>
<img src="https://i.imgur.com/nVaTJ3t.png" height="80%" width="80%" alt="SIEM Lab"/>
<br />
<br />
Creating a custom workbook in Sentinel by creating a query and pasting the same query (with the log created) again:  <br/>
<img src="https://i.imgur.com/K2VE1Wl.png" height="80%" width="80%" alt="SIEM Lab"/>
<br />
<br />
Changing the visualization of the data to the map option and using the settings to configure how the map will display the data (giving the final product map):  <br/>
<img src="https://i.imgur.com/LnU90Gv.png" height="80%" width="80%" alt="SIEM Lab"/>
<br />
<br />
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
