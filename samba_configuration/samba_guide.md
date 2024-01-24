# Samba Server Installation Documentation

## A. Introduction
### 1. Purpose
The aim of this project is to set up and configure Samba, a cross-platform file-sharing tool.

### 2. Integration with Linux Server
Setting up Samba as a Server facilitates resource sharing and exchange for work and collaboration efficiency.

## B. Installation and Configuration
### 1. Samba Installation
**Step 1 – System Update**
```bash
sudo apt update
Step 2 – Actual Samba Installation

bash
Copy code
sudo apt install samba
2. Share Configuration
Step 3 – Creating Directory for Sharing

bash
Copy code
sudo mkdir /share
Step 4 – Creating Files to be Shared on the Network

bash
Copy code
sudo touch /share/file{1..5}
Step 5 – Granting Permission Access

bash
Copy code
sudo chmod 777 /share
N.B: The important access is the last 7, granting Read, Write, Execute to Others (Everyone on the network); other permissions are optional.

Step 6 – Editing Samba Configuration File

bash
Copy code
sudo vim /etc/samba/smb.conf
Step 7 – Configuration File Settings

conf
Copy code
[public-file]
path = /share
public = yes
browseable = yes
read only = no
create mask = 0777
directory mask = 0777
    comment = "Public File Server"
Save and exit (:wq)

    Step 8 – Test Configuration

    bash
    Copy code
    sudo testparm
    Step 9 – Starting Samba

    bash
    Copy code
    sudo systemctl start smbd
    sudo systemctl status smbd
    sudo systemctl start nmbd
    C. User Authentication
    1. User Accounts
    Step 10 – Creating User Accounts

    bash
    Copy code
    sudo useradd –s /sbin/nologin azeez
    sudo useradd –s /sbin/nologin admin
    sudo useradd –s /sbin/nologin tech
    Step 11 – Assigning Password for Each User

    bash
    Copy code
    sudo smbpasswd –a azeez
    sudo smbpasswd –a admin
    sudo smbpasswd –a tech
    Step 12 – Log in to a Client’s Machine to Sync Samba

    For Linux users:
    Locate the "Files" application, click "Other Locations" at the bottom-left, then click. Below is a screenshot for clarity.

    Step 13 – Enter Server Address

    //smb:server-ip – Ubuntu Linux
    smb://server-ip – RedHat Linux
    \\server-ip – Windows OS
    Step 14 – Proceed to Connect

    Authentication is required using the created username and password on the Server.

    D. Security and Access Controls
    1. Firewall Configuration
    Step 15 – Disable Firewall

    bash
    Copy code
    sudo ufw disable
    N.B: This was done on the Server to enable traffic flow on the Samba network.

    2. Encryption and Authentication
    File authentication applied was the chmod 777 on the /shared resources, ensuring only registered users on the Samba network have access.

    E. Testing and Verification
    1. Access Testing
    Conducted tests on shared files from both Linux and Windows environments, including file modification and printing from a Windows environment.

    2. Error Handling
    Handled common errors related to mistyping server addresses for Windows and Linux environments.

    F. Maintenance and Upgrades
    1. Software Updates
    Keep Samba server up-to-date for security and performance.

    On Debian/Ubuntu:
    bash
    Copy code
    sudo apt update 
    sudo apt upgrade samba
    On Red Hat/CentOS:
    bash
    Copy code
    sudo yum update samba
    2. Monitoring Samba
    Methods for monitoring Samba, including viewing logs, using smbstatus, checking service status, monitoring system resources, and implementing external monitoring tools.

    G. Troubleshooting
    1. Logs and Diagnostics
    Accessing and interpreting Samba logs, common Samba issues, and their solutions.

    H. Integration with Other Services
    1. LDAP or Active Directory Integration
    LDAP Integration with Samba: Install required packages, configure LDAP client, edit Samba configuration for LDAP, and restart services.
    Active Directory Integration with Samba: Install required packages, join Samba to the Active Directory domain, configure Winbind, configure PAM and NSSwitch, and restart services.
    I. Conclusion
    Summarizing the main points and providing additional considerations for successfully setting up and configuring Samba on a Linux server for file sharing. Regular monitoring, updates, and troubleshooting are crucial for optimal functionality.
