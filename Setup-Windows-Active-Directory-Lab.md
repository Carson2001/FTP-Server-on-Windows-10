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

## Step 8. **Import file_svr.**

https://github.com/user-attachments/assets/d09d0b9f-df97-4ff6-99b8-7947dae538d6

## Step 9. **Create pfsense VM and initialize.**

https://github.com/user-attachments/assets/d3cf5c27-894f-4b3c-9b1b-59eccf99f6ff

https://github.com/user-attachments/assets/2ea8e2ae-59ba-488c-aeff-74223d707e27

## Step 10. **Change the hostname for all VMs.**

https://github.com/user-attachments/assets/73c9be0b-2be9-4555-8493-44532728be09

## Step 11. **Configure network settings on pfsense web GUI.**

https://github.com/user-attachments/assets/6e9aae10-5c6d-40d4-931c-5e44eb950e20

## Step 12. **Install AD DS and promote svr_DC to a Domain Controller (adlab.com).**

https://github.com/user-attachments/assets/f64eb0fd-df59-4957-883c-32d4fa066e6a

## Step 13. **Create domain users and host machines for your AD.**

https://github.com/user-attachments/assets/ad363784-3acd-4657-ada5-5878872878b2

## Step 14. **Ensure that you have accurately configured a static IPv4 Address for your Domain Controller within the same subnet as the LAN interface for the pfsense router. The DNS server should be the default gateway address of your host machine.**

https://github.com/user-attachments/assets/35f03d96-4b31-450b-9fbf-aa5f7aa444b9

## Step 15. **Install DHCP services on your Domain Controller.**

https://github.com/user-attachments/assets/cac0acc1-de59-4d4a-9290-ef47dc33bba2

## Step 16. **Configure a range of usable IPv4 addresses for your domain. Ensure that you have configured your DNS Server as the IPv4 Address of your Domain Controller. In my case, it is 192.168.0.2/24.**

https://github.com/user-attachments/assets/9104a82e-2243-4fea-ac15-007c48168a2a

## Step 17. **Add Domain Users to Remote Desktop Users due to a security feature in Windows 10 OS.**

https://github.com/user-attachments/assets/23615861-40f3-45d0-bfbc-6be961eff426

## Step 18. **Add both remote machines to adlab.com domain. Ensure that your remote machine has obtained an IPv4 address within range of the DNS servicer scope. Use the login credentials that were created under domain users to login to the newly added machines.**

https://github.com/user-attachments/assets/091abf13-265d-4a65-9787-8c1eddffac26

## Step 19. **Because file_svr is an export of the svr_DC virtual machine, use a tool called “sysprep” to create a unique SID.**
https://github.com/user-attachments/assets/6cc9d514-79ec-46f7-8036-165fc9b6dea0

## Step 20. **Add file_svr to the adlab.com domain.**

https://github.com/user-attachments/assets/c00b7997-7609-40ab-894c-b545b41fcbc2

## Completion:

You have successfully created a virtualized Active Directory environment. Ensure that all machines are connected to the adlab.com domain, can ping each other, and you have the necessary firewall configurations made to allow communication between clients. From here, you will be able to set GPO, security rules, and other administrative tasks to your environment.
