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

