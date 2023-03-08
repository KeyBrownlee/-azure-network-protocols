<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, DNS, HTTP/S, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

- Create a Windows 10 virtual machine and a Linux virtual machine
- Observe ICMP traffic: Install Wireshark on Windows 10 VM, filter for ICMP traffic only, ping the private IP address of the Linux VM. Open Network Security Group settings on Linux VM and disable incoming ICMP traffic
- Observe SSH traffic: From Windows 10 VM "SSH into" Linux VM using private IP address, type commands and observe traffic in wireshark
-  Oberve DNS traffic: In Windows 10 VM filter for DNS traffic only, in a command line nslookup a random website and observe the IP addresses being displayed 

<h2>Actions and Observations</h2>

<p>
<img src="https://i.imgur.com/NbHcBZT.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
After creating both Linux and Windows 10 virtual machines, Wireshark is downloaded in Windows 10 virtual machine
</p>
<br />
<p>
<img src="https://i.imgur.com/322oVn8.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<img src="https://i.imgur.com/z8SB9ih.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
ICMP filter is applied in Wireshark, and in commandline on Windows 10 virtual machine the private IP address of the Linux virutal machine is pinged. An inbound rule to deny ICMP traffic for the Linux virtual machine is set, and the Windows virtual machine is no longer receiving ICMP traffic from the Linux vitual machine
</p>
<br />
<p>
<img src="https://i.imgur.com/cpmmfK8.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
In Wireshark on the Windows virtual machine the filter is changed to SSH, in powershell we then essientially remote ito the Linux virtual machine via SSH
</p>
<br />
<p>
<img src="https://i.imgur.com/kZNH819.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
In Wireshark on the Windows virtual machine the filter is changed to DNS, in Powershell use "nslookup" followed by any website to discover the public IP addresses assigned to the website that may appear when users are browsing the sites. 
</p>
<br />
