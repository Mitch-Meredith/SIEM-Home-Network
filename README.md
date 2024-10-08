<h1>Implementing a SIEM on Home Network</h1>

<h2>Description</h2>
This Project consists of taking a Linode Web-Based Server and installing a SIEM enviroment onto it to monitor and implement security changes on my home network.  
<br />


<h2>Languages and Utilities Used</h2>

- <b>PowerShell</b> 
- <b>[Linode Web-Based Servers](https://www.linode.com/)</b>
- <b>[Wuzah](https://wazuh.com/)</b>

<h2>Environments Used </h2>

- <b>Windows 11</b>
- <b>Ubuntu 24.04 LTS</b>

<h2>Implementation walk-through:</h2>

<p align="center">
<b>Configure a new Linode:</b> <br/>
  - Pick Region nearest you <br/>
  - Pick Ubuntu OS <br/>
  - Pick Linode 4GB plan under the "Shared CPU" option
<img src="https://imgur.com/MT9i8ua.png" height="80%" width="80%"/>
<br />
<br />  
  - Name your server something related to this project <br/>
  - Create a secure Root Password (This is how you will log into the SSH) <br/>.
  <img src="https://imgur.com/vbLZ6AS.png" height="80%" width="80%"/>
<br />
<br />
<b>Wait for Linode to Provision the server</b>
  <img src="https://imgur.com/WydpHf9.png" height="80%" width="80%"/>
<br />
<br />
<b>SSH into the Server in PowerShell using "SSH Access"</b>
  <img src="https://imgur.com/HcMoN5G.png" height="80%" width="80%"/>
<br />
<br />
  - Type "Yes" for fingerprinting and type the Root Password from Earlier for when prompted
  <img src="https://imgur.com/QGPR0iW.png" height="80%" width="80%"/>
<br />
<br />
<b>Once Logged in, run the Curl Command for Wazah install</b><br/>
 - https://documentation.wazuh.com/current/quickstart.html 
  <img src="https://imgur.com/VWwdt5I.png" height="80%" width="80%"/>
<br />
<br />
- Once completed (could take a bit of time) you're given the User/Password <br/>
  <img src="https://imgur.com/XKKJXkJ.png" height="80%" width="80%"/>
<br />
<br />
<b>Grab the URL from the Linode Site</b>
  <img src="https://imgur.com/JbmcsOO.png" height="80%" width="80%"/>
<br />
<br />
- Add HTTPS:// infront of the the linode URL and Accept the Risk when prompted
  <img src="https://imgur.com/SnjhiAX.png" height="80%" width="80%"/>
<br />
<br />
<b>Now enter Username and Password provided by the install, and you're on the Wazuh Dashboard</b>
  <img src="https://imgur.com/f2BCvIW.png" height="80%" width="80%"/>
<br />
<br />
<b>Add a new Agent to the Host</b><br />
  -Go to Hamburger Menu > "Server Management" > "Endpoint Summary" > "Add new Agent" <br/>
  <img src="https://imgur.com/jZhJYZl.png" height="80%" width="80%"/>
<br />
<br />
<b>Follow the on-screens steps noting that the Server address will be the URL provided by Linode</b>
  <img src="https://imgur.com/KRgGFgB.png" height="80%" width="80%"/>
<br />
<br />
<b>Run the commands in Step 4 and 5 on the Agent PC in Powershell(Admin) </b><br/>
  -Note that if the Agent isnt able to connect to the host you might need to open ports 1514 and 1515 on your router
  <img src="https://imgur.com/ZtzyyqE.png" height="80%" width="80%"/>
<br />
<br />
<b>Once Agents are connected we're able to see all events and their severity, as well as perform audits on our agents and investigate security concerns on our machines in one place!</b>
  <img src="https://imgur.com/ojENB0m.png" height="80%" width="80%"/>
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
