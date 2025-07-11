# Hydra Password Guessing Lab Report

## Introduction
This lab demonstrates practical password guessing attacks against SSH and SMB services using Hydra, highlighting real-world vulnerabilities in weak password policies.

## Methodology

### 1. Password List Analysis
- Reviewed John the Ripper's default password list (`/usr/share/john/password.lst`)
- Counted total passwords: `cat /usr/share/john/password.lst | wc -l`
- Filtered passwords with specific characteristics using `pw-inspector`

### 2. SSH Password Guessing
1. Created test account: `sudo useradd monk`, set password to "master1"
2. Verified SSH service: `sudo netstat -nat | grep 22`
3. Launched xHydra against localhost (127.0.0.1) with SSH protocol
4. Configured to use "monk" as username and password.lst as dictionary
5. Successfully cracked password 

### 3. SMB Password Guessing
1. Targeted Windows 7 machine at 192.168.229.137
2. Configured xHydra with SMB protocol
3. Monitored traffic with: `sudo tcpdump -nn host 192.168.229.137`
4. Successfully cracked password using single thread

## Results
- SSH attack succeeded with 16 parallel threads
- SMB attack succeeded with single thread (protocol limitation)
- Password list contained 288 passwords meeting:
  - Minimum length 5
  - Containing numbers and lowercase letters

## Screenshots
![Password List Analysis](Images/password-list.png)  
*Figure 1: Password list analysis*

![SSH Attack](Images/ssh-attack.png)  
*Figure 2: SSH password guessing results*

![SMB Attack](Images/smb-attack.png)  
*Figure 3: SMB password guessing results*

## Conclusion
This lab demonstrated how weak passwords can be easily compromised through automated guessing attacks. The differences between SSH and SMB in handling parallel attempts were particularly noteworthy. Organizations should implement strong password policies and account lockout mechanisms to mitigate such attacks.
