# Windows Active Directory Environment Lab (Hyper-V)

## Summary

In this lab, you will:
- Set up Windows Active Directory in a virtualized environment.
- Configure private and external virtual adapters for LAN and WAN communication.
- Install AD DS and promote a virtual machine to domain controller.
- Manage users and computers within the small-scale virtual domain.

## Prerequisites

- Access to a virtualization platform (Hyper-V, VMware, Virtual Box).
- At least 8 GB of RAM for your host system.

## Steps

## Step 1. **Create a private and external adapter in your Windows Hyper-V environment.**
   
[https://github.com/user-attachments/assets/bc0f58e3-cdf9-4b11-baf0-9d1bc9b34d9f](https://github.com/user-attachments/assets/b82f3085-abc9-43a9-8fe1-24422880cf80)

https://github.com/user-attachments/assets/825d61a4-e112-438e-8d02-1da7119c25ba

## Step 2. **Create Svr-DC VM.**
   
https://github.com/user-attachments/assets/168ef5f2-1845-41bf-b4e5-aca311c77ced
   
5. **Install Windows Server 201 and create credentials.**
6. **Create c1win10.**
7. **Install Windows 10.**
8. **Repeat for c2win10.**
9. **Export svr-DC to create file-svr.**
10. **Create pfsense VM and initialize.**
11. **Change the hostname for all VMs.**
12. **Configure network settings on pfsense web GUI.**
13. **Install AD DS on the svr_DC.**
14. **Promote svr_DC to a Domain Controller (adlab.com).**
15. **Create domain users and host machines for your AD.**
16. **Ensure that you have accurately configured a static IPv4 Address for your Domain Controller within the same subnet as the LAN interface for the pfsense router. The DNS server should be the default gateway address of your host machine.**
17. **Install DHCP services on your Domain Controller.**
18. **Configure a range of usable IPv4 addresses for your domain. Ensure that you have configured your DNS Server as the IPv4 Address of your Domain Controller. In my case, it is 192.168.0.2/24.**
19. **Add Domain Users to Remote Desktop Users due to a security feature in Windows 10 OS.**
20. **Add both remote machines to adlab.com domain. Ensure that your remote machine has obtained an IPv4 address within range of the DNS servicer scope. Use the login credentials that were created under domain users to login to the newly added machines.**
21. **Because file_svr is an export of the svr_DC virtual machine, use a tool called “sysprep” to create a unique SID.**
22. **Add file_svr to the adlab.com domain.**

## Completion

You have successfully created a virtualized Active Directory environment. Ensure that all machines are connected to the adlab.com domain, can ping each other, and you have the necessary firewall configurations made to allow communication between clients. From here, you will be able to set GPO, security rules, and other administrative tasks to your environment.
