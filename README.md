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



