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

## Lab Topology:

![Topolgy](https://github.com/user-attachments/assets/b1ab1e80-2099-420a-8223-81433c8bf822)

## Instructions:

## Step 1. **Create a private and external adapter in your Windows Hyper-V environment.**
   
[https://github.com/user-attachments/assets/bc0f58e3-cdf9-4b11-baf0-9d1bc9b34d9f](https://github.com/user-attachments/assets/b82f3085-abc9-43a9-8fe1-24422880cf80)

https://github.com/user-attachments/assets/825d61a4-e112-438e-8d02-1da7119c25ba

Private adapters are utilized for communication within an internal LAN, whereas external adapters facilitate connections to external WANs. Both types are essential for establishing a secure environment for our virtual machines.

## Step 2. **Create Svr-DC VM.**
   
https://github.com/user-attachments/assets/168ef5f2-1845-41bf-b4e5-aca311c77ced

This server VM will be our domain controller (DC). DCs manage the domain where users and computers are interconnected and can provide additional services such as Active Directory Domain Services (AD DS), Dynamic Host Configuration Protocol (DHCP), and Domain Name System (DNS).
   
## Step 3. **Install Windows Server 2012 and create credentials.**

https://github.com/user-attachments/assets/96c1290c-36d0-4b13-92d4-b51ecff16a64

https://github.com/user-attachments/assets/0259a023-eb0a-4ad3-ad6f-b8a275663bea

I am using Windows Server 2012 R2 for this project, however, newer versions of Windows server are availabe. 

## Step 4. **Create c1win10.**

https://github.com/user-attachments/assets/e85e33e5-e996-4b71-88ca-3f9d1e0b5c97

This VM will be one of two Windows clients in our Active Directory environment. 

## Step 5. **Install Windows 10.**

https://github.com/user-attachments/assets/4fa29539-0a4e-40d9-93ae-4166626a27e2

## Step 6. **Repeat for c2win10.**

![repeat_c2win10](https://github.com/user-attachments/assets/1eb84f2a-a47e-4b7a-984d-cac0a7d664cf)

This VM will be the second of the Windows clients in our Active Directory environment. 

## Step 7. **Export svr-DC to create file-svr.**

https://github.com/user-attachments/assets/f51e9fd9-0d68-44f0-b869-eede49ba745d

To simplify the creation of our File Server, we can export a duplicate of our Domain Controller.

## Step 8. **Import file_svr.**

https://github.com/user-attachments/assets/d09d0b9f-df97-4ff6-99b8-7947dae538d6

After exporting the Domain Controller, we can import the duplicate and rename the machine. This VM will have the same ISO file and storage/memory allocation. Reinstalling Windows Server is not necessary after exporting a pre-configured machine. 

## Step 9. **Create pfsense VM and initialize.**

https://github.com/user-attachments/assets/d3cf5c27-894f-4b3c-9b1b-59eccf99f6ff

https://github.com/user-attachments/assets/2ea8e2ae-59ba-488c-aeff-74223d707e27

While connection to the internet is not necessary for Active Directory to function, installing a virtual router/firewall offers additional scalability and security for your enviornment. 

## Step 10. **Change the hostname for all VMs.**

https://github.com/user-attachments/assets/73c9be0b-2be9-4555-8493-44532728be09

Ensure that you have set hostnames that are easy to identify before you join your clients to the domain. 

## Step 11. **Configure network settings on pfsense web GUI.**

https://github.com/user-attachments/assets/6e9aae10-5c6d-40d4-931c-5e44eb950e20

Login to a client system, use an internet browser and type in the IPv4 address of the pfsense LAN interface (e.g. 192.168.0.1). Since we will be installing DHCP and DNS services on our Domain Controller, I disabled them on the pfsense machine via the web GUI interface.

## Step 12. **Install AD DS and promote svr_DC to a Domain Controller (adlab.com).**

https://github.com/user-attachments/assets/f64eb0fd-df59-4957-883c-32d4fa066e6a

Install Active Directory Domain Services (AD DS) on the server named svr_DC and promote it to act as a Domain Controller for the domain adlab.com, establishing it as the authoritative domain server.

## Step 13. **Create domain users and host machines for your AD.**

https://github.com/user-attachments/assets/ad363784-3acd-4657-ada5-5878872878b2

Set up user accounts and computer accounts within the Active Directory for all individuals and host machines that will be part of your network domain. 

## Step 14. **Ensure that you have accurately configured a static IPv4 Address for your Domain Controller,**

https://github.com/user-attachments/assets/35f03d96-4b31-450b-9fbf-aa5f7aa444b9

Configure a static IPv4 address for the Domain Controller to ensure it resides on the same subnet as the LAN interface of the pfSense router. Set the Domain Controller’s DNS server address to match the default gateway of your host machine.

## Step 15. **Install DHCP services on your Domain Controller.**

https://github.com/user-attachments/assets/cac0acc1-de59-4d4a-9290-ef47dc33bba2

Install and configure the DHCP server role on your Domain Controller to manage the dynamic distribution of IP addresses in your network.

## Step 16. **Configure a scope of usable IPv4 addresses for your DHCP Server.**

https://github.com/user-attachments/assets/9104a82e-2243-4fea-ac15-007c48168a2a

Define a specific range of IPv4 addresses that can be assigned to devices within your domain. Set the DNS server setting to point to your Domain Controller’s IP address, ensuring all devices use it for DNS resolution.

## Step 17. **Add Domain Users to Remote Desktop Users.**

https://github.com/user-attachments/assets/091abf13-265d-4a65-9787-8c1eddffac26

Because of security features in Windows 10 OS, the client machines will need to be added to remote desktop users as well as domain users. 

## Step 18. **Add both client machines to the adlab.com domain.**

https://github.com/user-attachments/assets/6cc9d514-79ec-46f7-8036-165fc9b6dea0

Ensure that your remote desktop users have obtained an IPv4 address within the range of the DHCP Server. Use the login credentials that were created under domain users to log in to the newly added machines

## Step 19. **Because file_svr is an export of the svr_DC virtual machine, use a tool called “sysprep” to create a unique SID.**

https://github.com/user-attachments/assets/23615861-40f3-45d0-bfbc-6be961eff426

Use the “sysprep” tool on file_svr, which is a cloned version of the svr_DC VM, to reset the system identification number (SID) to ensure it is unique within the network.

## Step 20. **Add file_svr to the adlab.com domain.**

https://github.com/user-attachments/assets/c00b7997-7609-40ab-894c-b545b41fcbc2

Integrate the file_svr machine into the adlab.com domain, allowing it to participate fully in domain-based network activities and security authentication processes.

## Completion:

You have successfully created a virtualized Active Directory environment. Ensure that all machines are connected to the adlab.com domain, can ping each other, and you have the necessary firewall configurations made to allow communication between clients. From here, you will be able to set GPO, security rules, and other administrative tasks to your environment.
