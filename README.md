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

<h2>Lab Overview</h2>

1. Create Windows and Ubuntu VMs in the same Virtual Network/Subnet.  
2. Observe ICMP (ping) traffic between VMs.  
3. Configure NSG rules to block/unblock ICMP.  
4. Capture and analyze SSH traffic.  
5. Capture DHCP traffic during IP renewal.  
6. Capture DNS queries using nslookup.  
7. Capture RDP traffic from Windows 10 VM.  


# Step 1: Create Azure Virtual Machines

1. Log into [Azure Portal](https://portal.azure.com/).
2. Create a **Resource Group**.
3. Create a **Windows 11 VM**:
   - Assign to previously created Resource Group
   - Allow it to create a new Virtual Network and Subnet
   - Enable RDP
4. Create an **Ubuntu VM**:
   - Assign to the same Resource Group and Virtual Network as Windows 10 VM
   - Authentication: Username/Password
   - Ensure same Subnet
5. Verify both VMs are in the same Virtual Network/Subnet.



<header>
  <h1>Network Traffic Analysis Lab</h1>
  <p>ICMP, DHCP, DNS, and SSH Packet Inspection using Wireshark</p>
</header>

<div class="container">


<div class="section">
    <h2>1. ICMP Traffic Analysis</h2>
    <p>
    Installed Wireshark inside of Windows VM and filtered for ICMP traffic to find the private IP of my Linux VM (echo request/replies).
      </p>
    <img width="1925" height="1077" alt="image" src="https://github.com/user-attachments/assets/409d4bf0-1896-4d75-b7ab-ce3457ce3805" />
    
  1. Initiate continuous ping from Windows 10 VM to Ubuntu VM:
  2. Open **NSG** associated with Ubuntu VM.
  3. Disable **inbound ICMP traffic**.
  4. Observe ping failures in Windows 10 VM (Wireshark + command line).
  5. Re-enable inbound ICMP traffic.
  6. Verify ping resumes successfully.
  7. Stop continuous ping: `Ctrl + C`.

    


  <div class="section">
    <h2>2. DHCP Traffic Analysis</h2>
    <p>
      This section demonstrates the DHCP handshake process by initiating "ipconfig/renew" including 
      <code>Discover</code>, <code>Offer</code>, <code>Request</code>, and <code>ACK</code>.
    </p>
    <img width="1894" height="945" alt="image" src="https://github.com/user-attachments/assets/1f664350-4bc7-48d8-9e89-4d33b227f35f" />

      Wireshark capture showing DHCP release, discover, offer, request, and acknowledgment packets.
   
  </div>

  <div class="section">
    <h2>3. DNS Query Analysis</h2>
    <p>
      DNS queries and responses were captured while resolving a domain name using 
      <code>nslookup</code>.
    </p>
    <img width="1908" height="1017" alt="image" src="https://github.com/user-attachments/assets/48c61a26-295e-4260-a914-bcc1e65e9aad" />

      DNS traffic showing queries and responses, including resolved IP addresses.
    
  </div>

   


  <div class="section">
    <h2>4. SSH Traffic Analysis</h2>
    <p>
      SSH traffic was captured during a secure remote login session. Packets are encrypted, 
      demonstrating secure communication over port 22.
    </p>
    <img width="1888" height="1008" alt="image" src="https://github.com/user-attachments/assets/3d74c693-dab1-40cb-abdf-c7ccc3b28e15" />

      Encrypted SSH packets captured in Wireshark along with a successful remote login session.
    
  </div>




</div>

</body>
</html>
