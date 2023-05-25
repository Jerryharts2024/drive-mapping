<p align="center">
<img src="https://user-images.githubusercontent.com/131130119/239724733-a34a4353-4aa7-420f-80b5-d1aa414441d7.png" alt="osTicket logo"/>
</p>

<h1>Drive Mapping - Map Network Drive Using Group Policy</h1>
This tutorial outlines prerequisites and implementation of network drive mapping using group policy. To understand drive mapping, kind of think of how files are shared accross different users on the same network. It involves folders, files and even an entire storage drive in a certain Windows computer.Or even cloud storage folder like that of OneDrive. Drive mapping essentially eases to how files are shared to different users connected to one network. It basically means making a specific drive available to other users connected to a common network
    <br />
 
  <h2>Video Demonstration</h2>

- ### [YouTube: How To Map a Network Drive Using Group Policy](https://youtu.be/0rPyNMxnIKc)

<h2>Environments and Technologies Used</h2>

- Amazon Web Services - AWS (Instance Machines/Compute)
- Domain Controller
- Server Manager
- A Client PC
- Remote Destop Connection (RDP)
- Group Policy Management

<h2>Operating Systems Used </h2>

- Windows Server 2022 (2 instances)
- Used as a DC and a Client

<h2>List of Prerequisites</h2>

- Create AWS instances (A Client and a Domain Controller) Join them to the DC domain
- Login to the DC
- In Active Directory Users and Computers Create New users
- Create New Security Groups
- Add Users to Security Groups
- Create the folder to be Mapped.
- Share the folder with the Security Group created
- Create Group policy Object (GPO)
- Edit GPO and Create a new Drive Map 
- Login to the Client Machine to see the Mapped Drive
- Try User in different Security Group


<h2>Deployment and Configuration Steps</h2>
<br />

<h3>Step 1: Setup Resources in AWS</h3>
<p>
<img src="https://user-images.githubusercontent.com/131130119/240813655-64dfacb1-ad19-4943-85cd-dd66789a3854.png" height="80%" width="80%" alt="Deployment and Configuration Steps"/>
</p>

- Create the Domain Controller VM
- Create the Client VM (Windows 10) named “Client-1”.
- Ensure that both VMs are already connected. This invovles setting up the network interface, setting active directory domain services And adding clients to Domain.  Go to ### [How to Deploy on-premises Active Directory within Azure Compute](https://github.com/jerryharts2024/configure-ad)

<br />





<h2>Deployment and Configuration Steps</h2>
<br />
<h3>Step 1: Setup Resources in Azure</h3>
<p>
<img src="https://user-images.githubusercontent.com/131130119/235380469-c636f956-79d5-43b5-957a-169052ec218b.png" height="80%" width="80%" alt="Deployment and Configuration Steps"/>
</p>

- Create the Domain Controller VM (Windows Server 2022) named “DC-1”
  - create new virtual machine
  - name the VM
- Take note of the Resource Group and Virtual Network (Vnet) that get created at this time
  - ensure that a resource group is created this time and intall the VM in the RG 
- Set Domain Controller’s NIC Private IP address to be static
  - In Azure, go to the network topology change the NIC IP to static
- Create the Client VM (Windows 10) named “Client-1”. Use the same Resource Group and Vnet that was created in Step 1.a
- Ensure that both VMs are in the same Vnet (you can check the topology with Network Watcher

<br />

