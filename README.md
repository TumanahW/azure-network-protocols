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

![Screenshot 2024-12-06 at 8 59 45 PM](https://github.com/user-attachments/assets/8fe3bd7c-633f-4382-97b7-54a625730d9a)


<p>Download Wireshark, Wireshark is a  protocol Analyzer that will allows us to  observe traffic coming from our Windows Machine.Once downloaded open Wireshark and start the packet capture by clicking on Ethernet and  the shark fin figure in the top left hand corner. </p>

![Screenshot 2024-12-06 at 8 59 45 PM](https://github.com/user-attachments/assets/39711938-bc5f-493d-8cb9-92ede91c64f6)

![Screenshot 2024-12-06 at 8 59 45 PM](https://github.com/user-attachments/assets/19bea3e2-e7b6-4eed-aeff-5c88ed395a99)


<p> You'll see this screen below running traffic on the back end. They are displaying IP Packets. IP Packers are small chunks of data sent over the internet that contains both the information being transfered and the necessary details like address for its destination. </p>

![Screenshot 2024-12-06 at 9 35 26 PM](https://github.com/user-attachments/assets/16e29bf5-2038-413c-be53-f876e7f03738)

Next, We'll filter for ICMP Traffic ( Internet Control Message Protocol) by typing <b>icmp</b> in the field above to only view icmp traffic. ICMP used for error reporting and diagnostics. ICMP is commonly used by network tools like <b>ping</b> and <b>traceroute</b> to test connectivity and troubleshoot network issues.

![Screenshot 2024-12-06 at 9 58 25 PM](https://github.com/user-attachments/assets/177c1be4-f6d1-4311-bedf-90865e9c4c3e)
