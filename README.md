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
- Try Login with User in different Security Group


<h2>Deployment and Configuration Steps</h2>
<br />

<h3>Step 1: Create AWS instances & Setup Resources in AWS</h3>
<p>
<img src="https://user-images.githubusercontent.com/131130119/240813655-64dfacb1-ad19-4943-85cd-dd66789a3854.png" height="80%" width="80%" alt="Deployment and Configuration Steps"/>
</p>

- Create the Domain Controller VM
- Create the Client VM (Windows 10) named “Client-1”.
- Ensure that both VMs are already connected. This invovles setting up the network interface, setting active directory domain services And adding clients to Domain.  Go to ### [How to Deploy on-premises Active Directory within Azure Compute](https://github.com/jerryharts2024/configure-ad)

<br />

<h3>Step 2: In Active Directory Users and Computers Create New users</h3>
<p>
<img src="https://user-images.githubusercontent.com/131130119/240815888-9afa5986-00eb-4114-9c3e-183d424e990a.png" height="80%" width="80%" alt="Deployment and Configuration Steps"/>
</p>

- In Active Directory Users and Computers Create New Organisational Unit and add a user to it. 
    - right click on the domain name, go to --> new --> organisational unit 
    - to add user, right click on the unit and go to --> New --> user --> and create new user.
    - For this sake of this demostration we have create an organisational unit called EMPLOYEE and we have added a user called Jane Doe to it. 

<br />

<h3>Step 3: In Active Directory Users and Computers Create Security and Add User Group</h3>
<p>
<img src="https://user-images.githubusercontent.com/131130119/240819396-5aa5b352-2569-4bfd-a810-099c2437e678.png" height="80%" width="80%" alt="Deployment and Configuration Steps"/>
</p>

- In Active Directory Users and Computers Create s Security Group and add the user to the group. 
    - right click on the domain name, go to --> new --> group 
    - to add user, right click on the user and go to --> property,  --> member of and add the user to the securtiy group.
    - this allows the user the rights and  permission to stuffs shared with the security group

<br />



<h3>Step :4  Create the folder to be Mapped Within the Network.</h3>
<p>
<img src="https://user-images.githubusercontent.com/131130119/240822302-fd6385c1-a54d-4f40-b0e8-b188165da340.png" height="80%" width="80%" alt="Deployment and Configuration Steps"/>
</p>

- To Create the folder to be Mapped Within the Network as a Drive. 
    - Go to C dirve and create a folder.
    - for the sake of our demostration, we created a folder named EMPLOYEE DATA

<br />


<h3>Step :5 Share the folder with the Security Group created.</h3>
<p>
<img src="https://user-images.githubusercontent.com/131130119/240826915-09a2668b-0f61-4846-864c-363bac065a81.png" height="80%" width="80%" alt="Deployment and Configuration Steps"/>
</p>

- To Share the folder with the Security Group created. 
    - Go to --> EMPLOYEE DATA --> properties --> sharing
    - add the folder (EMPLOYEE DATA) to the Employee security group.
    - this allows all the users in that group to be able to have access to the Employee data therefore while they are logged in, they should be able to see the drive named EMPLOYEE DATA and be able to read and write in the drive

<br />


<h3>Step :6 Create Group policy Object (GPO).</h3>
<p>
<img src="https://user-images.githubusercontent.com/131130119/240831639-f9b4d460-e67b-4cc2-bbfe-04172e9622cd.png" height="80%" width="80%" alt="Deployment and Configuration Steps"/>
</p>

- Create Group policy Object (GPO). 
    - go to --> active directory dashboard --> group policy management --> and create a GPO called EMPLOYEE GPO
<br />

<h3>Step :7  Edit GPO and Create a new Drive Map.</h3>
<p>
<img src="https://user-images.githubusercontent.com/131130119/240835346-22f18c5a-8ac4-4deb-b808-04960adbaabe.png" height="80%" width="80%" alt="Deployment and Configuration Steps"/>
</p>

- Edit GPO and Create a new Drive Map. 
- After creating the GPO, its time to map the Drive
    - go to GPO --> edit --> preferences --> window setting --> drive map (right click) --> New --> mapped drive
    - add EMPLOYEE DATA folder location  (this is the network path for the folder can be obtained in the property / sharing)
    - assign drive letter and make the drive visible by checking on show this drive.
    
<br />


<h3>Step :7 Login to the Client Machine to see the Mapped Drive.</h3>
<p>
<img src="https://user-images.githubusercontent.com/131130119/240857572-7c451cc1-d59a-4b96-bce6-369b13001689.png" height="80%" width="80%" alt="Deployment and Configuration Steps"/>
</p>

- Login to the Client Machine to see the Mapped Drive. 
- At this pooint, the network drive has been mapped. And we need to login to the client computer to see if it was successful.
- to do this, let's login to the client machine using Jane Doe. Remember Jane Doe is the only domain User who is also member of our employee security group
- Go to PC to see if the drive has been mapped.
<br />
