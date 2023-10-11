<h1>AD Home Lab w/ OPNsense</h1>

<h2>Description</h2>
In my home lab, I created a Windows VM victim with defense evasion techniques, integrated LimaCharlie for threat detection, and simulated attacks with an Kali Linux VM using Sliver (C2 Framework). I performed memory dumps, monitored activity, and executed defensive actions, demonstrating practical cybersecurity skills in a controlled environment. All credit goes to the original author Eric Capuano: https://blog.ecapuano.com/p/so-you-want-to-be-a-soc-analyst-intro
<br />


<h2>Languages and Utilities Used</h2>

- <b>Bash</b> 
- <b>VMware Workstation Pro 17</b>
- <b>PowerShell</b>

<h2>Environments Used </h2>

- <b>Windows 11 (22H2) <b/>
- <b>Ubuntu Desktop Virtual Machine (VM)</b>
- <b>Windows 11 (22H2) Virtual Machine (VM)</b>
- <b>OPNsense Firewall Virtual Machine </b>

<h2>Program walk-through:</h2>

<p align="center">
Disabled Microsoft Defender via Registry on the VM: <br/>
<img src="https://i.imgur.com/ghtRP1H.png" height="80%" width="80%" alt="Windows Defender Disabled"/>
<br />
<br />
Installed Sysmon64 on Windows 11 VM: <br/>
<img src="https://i.imgur.com/UlbN2iW.png" height="80%" width="80%" alt="Sysmon64 Installed"/>
<br />
<br />
Installed LimaCharlie EDR to detect threats on Windows 11 VM: <br/>
<img src="https://i.imgur.com/piro1bV.png" height="80%" width="80%" alt="LimaCharlie EDR Installed"/>
<br />
<br />
Installed Sliver a Command & Control (C2) Framework on Kali Linux VM: <br/>
<img src="https://i.imgur.com/mnhRFBV.png" height="80%" width="80%" alt="Sliver C2 Framework Installed"/>
<br />
<br />
Used a temporary python web server to dump the payload onto the Windows 11 VM: <br/>
<img src="https://i.imgur.com/L7h6yHa.png" height="80%" width="80%" alt="Sliver C2 Python Web Server"/>
<br />
<br />
Started C2 session and gained access to Windows 11 VM, able to get basic info: <br/>
<img src="https://i.imgur.com/EFai97T.png" height="80%" width="80%" alt="Sliver C2 Session"/>
<br />
<br />
We now take a look at LimaCharlie and see real-time view of the EDR telemetry & event logs from the Win11 VM
 <img src="https://i.imgur.com/a4ap216.png" height="80%" width="80%" alt="LimaCharlie Telemetry"/>
<br />
<br />
Using Sliver C2 Framework dumped the lsass.exe from memory
 <img src="https://i.imgur.com/GG5g6Ad.png" height="80%" width="80%" alt="Procdump LSASS.exe"/>
<br />
<br />
Created a detection rule on LimaChalie to generate a report anytime the detection occurred
 <img src="https://i.imgur.com/CVpfyzl.png" height="80%" width="80%" alt="Procdump LSASS.exe"/>
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
