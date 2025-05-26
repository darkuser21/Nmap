
# 🔒 Cyber Security Internship Report – Task 1  
Scan Your Local Network for Open Ports

👤 Name: Sanny Prajapati  
📅 Date: 26-May-2025  
🔗 GitHub Repo: [Insert GitHub Link Here]

---

## 🧠 Objective

The objective of this task is to perform basic network reconnaissance by scanning a local network for devices and their open ports using Nmap. This exercise helps in understanding how exposed services can pose security risks within a network environment.

---

## 🛠 Tools Used

- 🛡 [Nmap](https://nmap.org/) – Network scanning tool  
- 🧪 Wireshark (optional) – Packet analysis tool  

---

## 🧾 Steps Followed

### 1️⃣ Installed Nmap
- Downloaded and installed from the official Nmap website:  
  👉 https://nmap.org/download.html
- Verified installation via terminal:
    nmap --version
###  2️⃣ Found Local IP Range
- Used ipconfig (Windows) or ifconfig / ip a (Linux) to find the local IP.
# Example:
  ```bash
IP Address: 192.168.1.5 → Subnet: 192.168.1.0/24
  ```

### 3️⃣ Performed TCP SYN Scan

- Ran the following command to scan all devices on the local subnet:
  ```
  nmap -sS 192.168.1.0/24
  ```

This half-open SYN scan helps in quickly identifying open TCP ports.

### 4️⃣ Collected Results
 Output:
 ```
Nmap scan report for 192.168.1.1
Host is up (1.0s latency).
Not shown: 997 closed ports
PORT     STATE SERVICE
22/tcp   open  ssh
80/tcp   open  http
443/tcp  open  https
```
### 5️⃣ (Optional) Packet Capture with Wireshark
- Captured packets during scan using Wireshark.
Filtered packets using:
```
tcp.flags.syn == 1 && tcp.flags.ack == 0
```
Observed TCP SYN packets being sent to network hosts.

### 6️⃣ Researched Common Services
```
Port  Service  Description
22  SSH  Secure remote login
80  HTTP  Web server (unsecured)
443  HTTPS  Secure web server
139  NetBIOS  Windows file sharing
3389  RDP  Remote Desktop Protocol
```
 ### 7️⃣ Identified Potential Security Risks
SSH/HTTP ports may be vulnerable to brute-force or web-based attacks.
Unsecured services (e.g., Telnet) can expose sensitive data.
Services like RDP/SMB can be exploited if unpatched.
 ### 8️⃣ Saved Results
All Nmap results saved in:
Result.txt
