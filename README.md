<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, RDH, DNS, HTTP/S, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

<li>Create two virtual machines via Microsoft Azure</li>
<li>Observe ICMP Traffic</li>
<li>Observe SSH Traffic</li>
<li>Observe RDP Traffic</li>

<h2>Actions and Observations</h2>
<p>Create two virtual machines using Microsoft Azure. The first machine will be Windows 10 and the second will be Linux. </p>
<p>Download Wireshark, Wireshark is a  protocol Analyzer that will allows us to  observe traffic coming from our Windows Machine.Once downloaded open Wireshark and start the packet capture by clicking on Ethernet and  the shark fin figure in the top left hand corner. </p>

![Screenshot 2024-12-06 at 8 59 45 PM](https://github.com/user-attachments/assets/19bea3e2-e7b6-4eed-aeff-5c88ed395a99)

<p> You'll see this screen below running traffic on the back end. They are displaying IP Packets. IP Packers are small chunks of data sent over the internet that contains both the information being transfered and the necessary details like address for its destination. </p>

![Screenshot 2024-12-06 at 9 35 26 PM](https://github.com/user-attachments/assets/16e29bf5-2038-413c-be53-f876e7f03738)

Next, We'll filter for ICMP Traffic ( Internet Control Message Protocol) by typing <b>icmp</b> in the field above to only view icmp traffic. ICMP used for error reporting and diagnostics. ICMP is commonly used by network tools like <b>ping</b> and <b>traceroute</b> to test connectivity and troubleshoot network issues.

![Screenshot 2024-12-06 at 9 58 25 PM](https://github.com/user-attachments/assets/177c1be4-f6d1-4311-bedf-90865e9c4c3e)

<p> Open the Windows Powershell,  and ping the private IP address of  the Linux VM  to test for connectivity. </p>

![Screenshot 2024-12-06 at 11 16 46 PM](https://github.com/user-attachments/assets/3d08f6db-5cfb-43a5-8edf-2ac4b7147f52)

<p> Next, We will filter out SSH traffic in wire shark and send a ping request from our Windows Virtual machine to our Linux virtual Machine. SSH stands for Secure Shell and it's a network protocol uses port 22 and allows for client and server to communicate via an encrypted connected. </p>
<p> We will connect to SSH in linux machine  by typing into powershell ssh username  @ IP Address <b>ssh labuser@ 10.0.0.5)</b>. Next, type yes and then input password  and you will see the user prompt will change to Linux and you are in the Linux virtual machine. </p>

![Screenshot 2024-12-07 at 3 26 38 PM](https://github.com/user-attachments/assets/217e4c50-317e-4109-b2df-17668158b65b)

<P> In the image below, we can see that ssh traffic was filtered and encypted. It was sent from the source to the destination. We can see for the selected packet 30372 that the source packet 51843 sent encrypted data to port 22 and SSH uses port 22.  </P>

![Screenshot 2024-12-07 at 3 47 00 PM](https://github.com/user-attachments/assets/a26b6f45-991b-4480-83b5-06422a52fde0)

 <p> For RDP ( Remote Desk Top Protocol) we will filter out RDP traffic in wireshark. Type <b>tcp.port = =3389</b> and you will see that RDP is contantly running. The reason for this is that RDP is constantly streaming a connection  and image of the desktop.</p>
 
![Screenshot 2024-12-07 at 4 17 27 PM](https://github.com/user-attachments/assets/195eb815-bd89-48c3-9027-8e7c5fef4b28)

 

