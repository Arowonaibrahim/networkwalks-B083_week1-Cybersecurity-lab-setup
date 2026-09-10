`**`CYBERSECURITY LAB ENVIRONMENT SETUP`**`

**PROJECT OVERVIEW**

This project involves creating an isolated cybersecurity laboratory using VirtualBox and Kali Linux.
The purpose of the lab is to provide a safe environment for practicing cybersecurity activities such as network scanning, reconnaissance, vulnerability assessment, packet analysis, and penetration testing.
The lab uses a private virtual network, allowing additional virtual machines to be added later for authorized security testing.

**OBJECTIVES**

The main objectives of this project are to:
  •	Install and configure VirtualBox.
  •	Install and set up Kali Linux as a virtual machine.
  •	Create a private NAT Network.
  •	Configure network connectivity on Kali Linux.
  •	Assign a fixed IP address to the Kali virtual machine.
  •	Test network and DNS connectivity.
  •	Create a clean VM snapshot for recovery.
  •	Document the setup process.
  •	Prepare the laboratory for future cybersecurity exercises.

**PURPOSE OF THE LAB**

The laboratory provides a controlled environment for cybersecurity learning and authorized security testing.
It can be used for:
  •	Network reconnaissance
  •	Port scanning
  •	Vulnerability assessment
  •	Packet analysis
  •	Web security testing
  •	Exploitation practice
  •	Testing cybersecurity tools
Note: The laboratory should only be used on systems that are owned by you or where you have permission to perform security testing.

**LAB ARCHITECTURE**

The laboratory is built using VirtualBox and Kali Linux.
The main Kali Linux machine is connected to a private NAT Network. Other virtual machines can be connected to the same network later and used as targets for authorized security exercises.
<img width="1301" height="734" alt="Screenshot 2026-09-10 092338" src="https://github.com/user-attachments/assets/4c6c7bd5-312a-4322-b833-1e12fca57ad0" />


**LAB CONFIGURATION**

Component	Configuration
Host Operating System:	Windows 11
Host RAM:	8 GB
Processor:	Intel Core i5
Hypervisor:	VirtualBox 7.2
Security Operating System:	Kali Linux 2026.2
Kali RAM:	4096 MB
Virtual Network:	NAT Network
Network Address:	10.0.2.0/24
Kali IP Address:	10.0.2.2/24
Default Gateway:	10.0.2.1
DNS Server:	8.8.8.8
Future VM Range:	10.0.0.3–10.0.0.99

**LAB SETUP PROCEDURE**

Step 1:
  7-Zip was installed to extract the Kali Linux virtual machine package because the package may be provided as a .7z archive.
Step 2:
  VirtualBox was installed and used as the virtualization platform for creating and running the Kali Linux virtual machine.
Step 3: 
  A dedicated NAT Network was created in VirtualBox.
The network was configured as follows:
  •	Network Name: NatNetwork
  •	IPv4 Prefix: 10.0.0.0/24
  •	DHCP: Enabled
  •	IPv6: Disabled
The NAT Network allows multiple virtual machines connected to the same network to communicate with one another while still having external network connectivity.
This also makes it possible to add attacker and target machines to the same cybersecurity laboratory in the future.
Step 4: Import Kali Linux
  Kali Linux was downloaded and imported into VirtualBox as a virtual machine.
The network adapter was configured as follows:
  •	Adapter: Adapter 1
  •	Attached to: NAT Network
  •	Network: NatNetwork
  •	RAM: 4096 MB
A shared folder was also configured to allow files to be transferred between the Windows host and the Kali Linux virtual machine.
Step 5: Configure the Kali Linux Network
  The network settings of Kali Linux were configured using a consistent IPv4 address.
The configuration was:
  IP Address:     10.0.2.2
  Subnet Mask:    255.255.255.0
  Gateway:        10.0.2.1
  DNS:            8.8.8.8
Using a fixed IP address makes it easier to identify and access the Kali machine during future laboratory exercises.

Step 6: Create a Clean VM Snapshot
  After completing the initial configuration, a VirtualBox snapshot was created.
Snapshot name:
  Ibrahim_project
The snapshot serves as a clean backup of the laboratory environment.
If the system becomes misconfigured during future experiments, the snapshot can be restored to return the machine to its original working state.
<img width="795" height="384" alt="Screenshot 2026-09-10 090304" src="https://github.com/user-attachments/assets/6af89917-7c37-40a3-8013-90b9d939506b" />
<img width="1600" height="775" alt="VirtualBox_kali lin_10_09_2026_09_15_22" src="https://github.com/user-attachments/assets/320fc1ba-cf43-41b5-8ad8-fe989205f8d4" />
<img width="1600" height="775" alt="VirtualBox_kali lin_10_09_2026_09_21_07" src="https://github.com/user-attachments/assets/5cd275c2-90e4-4481-961b-a077ea825985" />

<img width="819" height="574" alt="Screenshot 2026-09-10 100809" src="https://github.com/user-attachments/assets/b64884a5-1dde-4895-925d-2aa6ceb8fa48" />

**LAB VERIFICATION**

After completing the setup, several tests were performed to confirm that the laboratory was working correctly.
1. Check IP Address
   
    ip a

This was used to confirm that the Kali machine received the correct IP address.
Expected result: 10.0.2.2/24

2. Test Gateway
   
    ping 10.0.2.1

This was used to check communication between Kali Linux and the network gateway.
Expected result: Successful replies.

3. Test Internet Connectivity
   
    ping 8.8.8.8

This was used to confirm that Kali Linux could communicate with the Internet.
Expected result: Successful replies.

4. Verify the Snapshot
The clean snapshot was restored and the network configuration was checked again.

    ip a

The original network configuration should be restored successfully.

**PROBLEMS ENCOUNTERED**

One of the problems encountered was losing Internet connectivity after configuring the static IP address. I also experienced a VirtualBox hardware virtualization error when trying to start the virtual machine.

**SOLUTIONS**

I checked the network configuration and corrected the settings to restore Internet access. For the VirtualBox error, hardware virtualization was enabled in the computer's BIOS settings, after which Kali Linux started properly.

**WHAT I LEARNED**

Through this project, I learned how to build and configure a virtual environment for cybersecurity practice.
1. NAT and NAT Network
I learned that standard NAT and NAT Network configurations have different purposes.
A NAT Network allows multiple virtual machines to communicate with each other while also providing external network connectivity.
2. Virtual Machine Networking
I learned how virtual network adapters connect virtual machines to different networks and how network settings affect communication between machines.
3. Static IP Configuration
I learned how to configure and verify IPv4 addresses, subnet masks, gateways, and DNS settings in Kali Linux.
4. VM Snapshots
I learned the importance of creating a clean snapshot before carrying out experimental or risky activities.
A snapshot provides a reliable recovery point if something goes wrong during a cybersecurity exercise.
5. Documentation
I learned that proper documentation of configurations, commands, problems, and solutions is an important part of a professional cybersecurity project.

**SECURITY AND ETHICAL USE** 

This laboratory is intended for educational purposes and authorized security testing only.
All security testing should be performed on systems that are owned by the user or where permission has been given to perform testing.

**TOOLS AND RESOURCES**

  •	7-Zip
  •	VirtualBox
  •	Kali Linux

**PROJECT INFORMATION**

Program: Cybersecurity
Project: Cybersecurity and Penetration Testing Lab Setup
Platform: VirtualBox and Kali Linux
Network: 10.0.2.0/24
Kali IP: 10.0.2.2

**AUTHOR INFORMATION**

Name: Arowona Ibrahim Olanrewaju
Linkedin: https://www.linkedin.com/in/ibrahim-arowona-26709140a?utm_source=share_via&utm_content=profile&utm_medium=member_android

