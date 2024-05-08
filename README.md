# How to create an FTP server on Windows 10 using Virtual Box:
Welcome! This project is designed for educational purposes, aimed at guiding users through the process of establishing communication between two virtual machines via FTP services. Using Command Prompt, FTP, HTTP, and network configuration, I'll demonstrate how to establish communication within a virtualized environment. By following the step-by-step instructions provided below, users will gain hands-on experience in configuring network settings and deploying services.

### Needed Materials:
* Oracle Virtual Box
* Windows 10 ISO Image File
* 2 Running Virtual Machines

### Step 1) Diable Windows Firewall On Both VMs:
Disabling the Windows firewall is often not necessary to use FTP services, but it can sometimes appear that way if the firewall is blocking the necessary ports for FTP communication. FTP (File Transfer Protocol) typically uses two ports: 21 for control (FTP commands) and 20 for data transfer. If the Windows firewall is enabled and not properly configured to allow FTP traffic through these ports, it can block the FTP connection. In such cases, users might resort to disabling the firewall as a quick solution.

https://github.com/Carson2001/Windows-10-FTP-Server/assets/154708874/6c5840eb-ae27-434b-a77f-7601f1f063e7

### Step 2) Enable Applicable Features & Services On The Server VM:

https://github.com/Carson2001/Windows-10-FTP-Server/assets/154708874/10dd0642-1246-463b-85c5-d8b1e8cb2b63

### Step 3) Create A Shared Folder On The Server VM:

https://github.com/Carson2001/Windows-10-FTP-Server/assets/154708874/0525a75d-7163-4fb7-9d6e-9fb09356c817

### Step 4) Statically Configure IPv4 Settings On Both VMs:

https://github.com/Carson2001/Windows-10-FTP-Server/assets/154708874/e89c0bc7-b536-4996-8cf7-12f3aea1aebb

https://github.com/Carson2001/Windows-10-FTP-Server/assets/154708874/c8d01f46-05a0-4a89-91fa-e0b3188c4ea3

### Step 6) Ping To Verify Connectivity:

https://github.com/Carson2001/Windows-10-FTP-Server/assets/154708874/e3bac2bd-a16f-459f-aae3-709371c6e079

### Step 7) Create FTP And HTTP Site Using Windows IIS: 

https://github.com/Carson2001/Windows-10-FTP-Server/assets/154708874/ac9cc175-0cd1-44a0-b20e-ec5a830d6b5e

### Step 8) Access Shared Files From The Client VM:

https://github.com/Carson2001/Windows-10-FTP-Server/assets/154708874/f7843882-3be1-4d97-beff-931938c0b578










