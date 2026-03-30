<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Analysis Lab"/>
</p>

<h1>Analyzing Network Traffic and Configuring NSGs in Azure</h1>

In this lab, I explored how network traffic flows between Azure Virtual Machines by using Wireshark to capture and analyze packets. I also worked with Network Security Groups (NSGs) to control and filter traffic, helping me better understand how security rules impact communication between systems.

<h2>Technologies and Tools Used</h2>

- Microsoft Azure (Virtual Machines, Virtual Networking)
- Remote Desktop Protocol (RDP) for remote system access
- Command-Line Interface (PowerShell, Bash)
- Wireshark (Network Traffic Analysis and Packet Capture)
- Network Protocols: ICMP, DNS, HTTP/HTTPS, SSH, RDP
- Network Security Groups (NSGs) for traffic filtering and access control


<h2>Operating Systems</h2>

- Windows 10/11
- Ubuntu Server 24.04

<h2>High-Level Steps</h2>

- Deployed and configured Windows and Ubuntu Virtual Machines in Microsoft Azure
- Established remote access using RDP to manage the Windows VM
- Installed and configured Wireshark to capture live network traffic
- Generated traffic using protocols such as ICMP, DNS, and HTTP to analyze packet behavior
- Applied protocol filters in Wireshark to isolate and inspect specific traffic types
- Configured Network Security Group (NSG) rules to allow and deny traffic
- Tested connectivity after rule changes to validate how NSGs impact network communication




<header>
  <h1>Network Traffic Analysis Lab</h1>
  <p>DHCP, DNS, and SSH Packet Inspection using Wireshark</p>
</header>

<div class="container">

  <div class="section">
    <h2>1. DHCP Traffic Analysis</h2>
    <p>
      This section demonstrates the DHCP handshake process including 
      <code>Discover</code>, <code>Offer</code>, <code>Request</code>, and <code>ACK</code>.
    </p>
    <img src="images/dhcp.png" alt="DHCP Capture">
    <p class="caption">
      Wireshark capture showing DHCP release, discover, offer, request, and acknowledgment packets.
    </p>
  </div>

  <div class="section">
    <h2>2. DNS Query Analysis</h2>
    <p>
      DNS queries and responses were captured while resolving a domain name using 
      <code>nslookup</code>.
    </p>
    <img src="images/dns.png" alt="DNS Capture">
    <p class="caption">
      DNS traffic showing queries and responses, including resolved IP addresses.
    </p>
  </div>

  <div class="section">
    <h2>3. SSH Traffic Analysis</h2>
    <p>
      SSH traffic was captured during a secure remote login session. Packets are encrypted, 
      demonstrating secure communication over port 22.
    </p>
    <img src="images/ssh.png" alt="SSH Capture">
    <p class="caption">
      Encrypted SSH packets captured in Wireshark along with a successful remote login session.
    </p>
  </div>

</div>

</body>
</html>
