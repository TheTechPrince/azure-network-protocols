<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, I observe various network traffic to and from Azure Virtual Machines using Wireshark as well as experiment with Network Security Groups. <br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (ICMP, SSH, DHCP, DNS, RDP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

- Create 2 virtual machines (windows 10 & linux)
- Use microsoft remote desktop to connect to VM1 (windows 10)
- Install wireshark
- Use wireshark, powershell and VM2's private IP address to inspect network traffic

<h2>Actions and Observations</h2>

<p>
<img src="https://i.imgur.com/bOFzGU1.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
- After downloading wireshark and launched successfully. 
- Live traffic started to get very active.
</p>
<br />

<p>
<img src="https://i.imgur.com/wmsB7Mj.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
- Ceased ICMP's traffic on VM2's firewall by creating an inbound security role in VM's network security group and denying the traffic. 
- The ping timed out and VM2 was unable to receive and send a reply, then went back and enabled ICMP traffic again.  
</p>
<br />

<p>
<img src="https://i.imgur.com/Oosw72n.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
- Decided to use Disney.com as an example to find what traffic and IP addresses that disney.com use by typing nslookup. 
</p>
<br />

<p>
<img src="https://i.imgur.com/zulH3PT.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p> - Last, I observed the RDP traffic using tcp.port == 3389. Despite unable to see traffic movement, the traffic was busy due to a live RDP session on VM1.
<br /
