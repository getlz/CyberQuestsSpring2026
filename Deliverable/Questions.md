## Question 1

**Question:**
What service appears to be running on port 2200?

**Answer:**
Secure Shell (SSH)

**Explanation:**
Traffic on port 2200 was analyzed using Wireshark. By inspecting packets and applying an `ssh` filter, the protocol was identified as SSH. This was confirmed by packet details showing “SSH Protocol” and the presence of an SSH version string (e.g., SSH-2.0-OpenSSH), indicating that Secure Shell was running on port 2200, even though it is a non-standard port.

---

## Question 2

**Question:**
Which IP address had port 2200 open?

**Answer:**
10.1.10.33

**Explanation:**
The attacker IP (172.31.255.28) was observed scanning multiple internal hosts. Most targets responded with reset (RST) packets, indicating closed ports. However, 10.1.10.33 responded with a successful connection on port 2200, and SSH traffic was established. This confirms that port 2200 was open on 10.1.10.33.

---

## Question 3

**Question:**
Which version of SSH was the attacker using?

**Answer:**
OpenSSH 5.3p1

**Explanation:**
Within the packet data, the SSH handshake revealed the version string “SSH-2.0-OpenSSH_5.3p1”. This identifies the exact version of the SSH client used by the attacker during the connection attempt.

---

## Question 4

**Question:**
It appears that after running a scan, the attackers made connections to each of the open ports. Which of the following tools was most likely used to establish those connections?

**Answer:**
Netcat

**Explanation:**
After identifying open ports, attackers commonly use Netcat to manually connect to services and interact with them. The observed behavior of connecting to multiple ports after scanning aligns with how Netcat is used for testing and communication with open services.

## Question 5

**Answer:**  
10.1.10.16  

**Explanation:**  
I filtered for port 23 in Wireshark and looked at how each IP responded. If the port was open, it would return SYN-ACK, but if it was closed it returned RST. The IP 10.1.10.16 kept returning RST responses, so that means port 23 was not open on that machine.


## Question 6

**Answer:**  
4.0 seconds  

**Explanation:**  
I filtered for the scan traffic using SYN packets on port 23 and looked at the Time column. Then I found the first scan packet and the last one and subtracted the times. The difference came out to about 4 seconds, so that’s how long the scan took.


## Question 7

**Answer:**  
TCP 2200  

**Explanation:**  
I checked which ports were actually being scanned by looking for repeated SYN packets. Ports 23, 80, and 3389 showed up a lot across different IPs, meaning they were part of the scan. Port 2200 only showed up once and didn’t have that same pattern, so it wasn’t part of the scan.

## Question 8

**Answer:**  
1  

**Explanation:**  
I filtered for port 3389 and looked for SYN-ACK responses, which indicate the port is open. Most IPs returned RST, meaning closed, but only one IP actually responded with SYN-ACK. So only one machine had port 3389 open.


## Question 9

**Answer:**  
10.1.10.15 and 10.1.10.13  

**Explanation:**  
I compared how different IPs responded to the scans on ports 23, 80, and 3389. Both 10.1.10.15 and 10.1.10.13 behaved the same way and returned RST for all of them, meaning everything was closed. Since their behavior matched exactly, they’re likely the same type of device.


## Question 10

**Answer:**  
10.1.10.20  

**Explanation:**  
I looked for the IP that had more activity and open ports compared to the others. Most devices were mostly closed, but 10.1.10.20 had more open responses (SYN-ACK). That suggests it’s running more services, which matches what an HMI would look like.
