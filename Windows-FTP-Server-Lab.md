# How to create an FTP server on Windows 10 using Virtual Box:
Welcome! This project is designed to guide users through the process of establishing communication between two virtual machines via FTP services. Using Command Prompt, FTP, HTTP, and network configuration, I'll demonstrate how to establish communication within a virtualized environment. By following the step-by-step instructions provided below, users will gain hands-on experience in configuring network settings and deploying services. ***This project is not affiliated with any company and is strictly for educational purposes.***

### Needed Materials:
* Oracle Virtual Box
* Windows 10 ISO Image File
* 2 Running Virtual Machines

### Step 1) Disable Windows Firewall On Both VMs:
For the objectives of this lab, we have temporarily disabled the software-based firewall on both virtual machines (VMs) to enable FTP communication. It is important to recognize the potential security risks associated with disabling firewalls in professional environments.

https://github.com/Carson2001/Windows-10-FTP-Server/assets/154708874/6c5840eb-ae27-434b-a77f-7601f1f063e7

### Step 2) Enable Applicable Features & Services On The Server VM:
Launch the "Turn Windows Features on or off" utility. You can access it by searching in the Start menu or by pressing the Windows key, typing "Turn Windows Features on or off," and hitting Enter. Upon opening the utility, a list of Windows features available for activation or deactivation will be displayed. Navigate through the list until you locate "Internet Information Services." Tick the box adjacent to it to enable IIS. To activate FTP services, mark the checkbox next to "FTP Server." Optionally, you can expand the "FTP Server" category to activate additional FTP features like FTP Extensibility and FTP Service. After selecting the desired features, click "OK" to implement the changes. Windows will initiate the installation of the chosen features, which might take a few moments. Upon completion of the installation process, you can close the "Turn Windows Features on or off" utility.

https://github.com/Carson2001/Windows-10-FTP-Server/assets/154708874/10dd0642-1246-463b-85c5-d8b1e8cb2b63

### Step 3) Create A Shared Folder On The Server VM:

https://github.com/Carson2001/Windows-10-FTP-Server/assets/154708874/0525a75d-7163-4fb7-9d6e-9fb09356c817

### Step 4) Statically Configure IPv4 Settings On Both VMs:
When I first set up my VMs, I set them to connect using the same network adapter and to receive IP addresses automatically via DHCP. However, you can manually set your IP addressing following the instructions in the video below. Just ensure that the VMs are configured with matching network addresses and subnet masks.

https://github.com/Carson2001/Windows-10-FTP-Server/assets/154708874/e89c0bc7-b536-4996-8cf7-12f3aea1aebb

https://github.com/Carson2001/Windows-10-FTP-Server/assets/154708874/c8d01f46-05a0-4a89-91fa-e0b3188c4ea3

### Step 6) Ping To Verify Connectivity:

https://github.com/Carson2001/Windows-10-FTP-Server/assets/154708874/e3bac2bd-a16f-459f-aae3-709371c6e079

### Step 7) Create FTP And HTTP Site Using Windows IIS: 

https://github.com/Carson2001/Windows-10-FTP-Server/assets/154708874/ac9cc175-0cd1-44a0-b20e-ec5a830d6b5e

### Step 8) Access Shared Files From The Client VM:

https://github.com/Carson2001/Windows-10-FTP-Server/assets/154708874/f7843882-3be1-4d97-beff-931938c0b578










