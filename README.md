# Hydra-Password-Guessing-Demo

This lab demonstrates password guessing attacks using Hydra against SSH and SMB services, highlighting the importance of strong password policies.

## Lab Objectives
- Perform password guessing attacks on SSH and SMB services
- Analyze password list characteristics
- Understand protocol differences in handling authentication attempts

## Tools Used
- Kali Linux
- Hydra (xHydra GUI version)
- John the Ripper's password list
- Windows 7 (for SMB target)
- tcpdump (for traffic analysis)

## Key Findings
1. SSH allowed parallel login attempts (16 threads by default)
2. SMB required single-threaded attempts due to being stateful
3. Default password lists contain many weak, easily guessable passwords
4. Many systems remain vulnerable to basic password guessing attacks


## Getting Started
To replicate this lab:
1. Set up Kali Linux and Windows 7 VMs
2. Install Hydra: `sudo apt install hydra hydra-gtk`
3. Review the [Commands.md](Commands.md) file for all lab commands
4. See the full [Lab Report](Lab-Report.md) for detailed methodology

## Security Note
This lab was conducted in a controlled environment for educational purposes only. Always obtain proper authorization before testing any systems.
