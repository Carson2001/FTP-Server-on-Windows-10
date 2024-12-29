# Windows Active Directory Environment Lab (Hyper-V)

## Summary:

In this lab, you will:
- Set up Windows Active Directory in a virtualized environment.
- Configure private and external virtual adapters for LAN and WAN communication.
- Install AD DS and promote a virtual machine to domain controller.
- Manage users and computers within the small-scale virtual domain.

## Prerequisites:

- Access to a virtualization platform (Hyper-V, VMware, Virtual Box).
- At least 8 GB of RAM for your host system.

## Instructions:

## Step 1. **Create a private and external adapter in your Windows Hyper-V environment.**
   
[https://github.com/user-attachments/assets/bc0f58e3-cdf9-4b11-baf0-9d1bc9b34d9f](https://github.com/user-attachments/assets/b82f3085-abc9-43a9-8fe1-24422880cf80)

https://github.com/user-attachments/assets/825d61a4-e112-438e-8d02-1da7119c25ba

## Step 2. **Create Svr-DC VM.**
   
https://github.com/user-attachments/assets/168ef5f2-1845-41bf-b4e5-aca311c77ced
   
## Step 3. **Install Windows Server 2012 and create credentials.**

https://github.com/user-attachments/assets/96c1290c-36d0-4b13-92d4-b51ecff16a64

https://github.com/user-attachments/assets/0259a023-eb0a-4ad3-ad6f-b8a275663bea

## Step 4. **Create c1win10.**

https://github.com/user-attachments/assets/e85e33e5-e996-4b71-88ca-3f9d1e0b5c97

## Step 5. **Install Windows 10.**

https://github.com/user-attachments/assets/4fa29539-0a4e-40d9-93ae-4166626a27e2

## Step 6. **Repeat for c2win10.**

![repeat_c2win10](https://github.com/user-attachments/assets/1eb84f2a-a47e-4b7a-984d-cac0a7d664cf)

## Step 7. **Export svr-DC to create file-svr.**

https://github.com/user-attachments/assets/f51e9fd9-0d68-44f0-b869-eede49ba745d

## Step 8. **Create pfsense VM and initialize.**

https://github.com/user-attachments/assets/d3cf5c27-894f-4b3c-9b1b-59eccf99f6ff

https://github.com/user-attachments/assets/2ea8e2ae-59ba-488c-aeff-74223d707e27

## Step 9. **Change the hostname for all VMs.**

https://github.com/user-attachments/assets/73c9be0b-2be9-4555-8493-44532728be09

## Step 10. **Configure network settings on pfsense web GUI.**

## Step 11. **Install AD DS and promote svr_DC to a Domain Controller (adlab.com).**

## Step 12. **Create domain users and host machines for your AD.**

## Step 13. **Ensure that you have accurately configured a static IPv4 Address for your Domain Controller within the same subnet as the LAN interface for the pfsense router. The DNS server should be the default gateway address of your host machine.**

## Step 14. **Install DHCP services on your Domain Controller.**

## Step 15. **Configure a range of usable IPv4 addresses for your domain. Ensure that you have configured your DNS Server as the IPv4 Address of your Domain Controller. In my case, it is 192.168.0.2/24.**

## Step 16. **Add Domain Users to Remote Desktop Users due to a security feature in Windows 10 OS.**

## Step 17. **Add both remote machines to adlab.com domain. Ensure that your remote machine has obtained an IPv4 address within range of the DNS servicer scope. Use the login credentials that were created under domain users to login to the newly added machines.**

## Step 18. **Because file_svr is an export of the svr_DC virtual machine, use a tool called “sysprep” to create a unique SID.**

## Step 19. **Add file_svr to the adlab.com domain.**

## Completion:

You have successfully created a virtualized Active Directory environment. Ensure that all machines are connected to the adlab.com domain, can ping each other, and you have the necessary firewall configurations made to allow communication between clients. From here, you will be able to set GPO, security rules, and other administrative tasks to your environment.
