![image](https://github.com/user-attachments/assets/d9f450f3-770c-412e-b89b-b3f2a1b6e1f3)
# osTicket-Post-Installation-Configuration
This tutorial outlines post-install configuration for the open-source help desk ticketing system osTicket.
# Environments and Technologies Used
+ Microsoft Azure
+ Remote Desktop
+ Internet Information Services
# Operating systems Used
+ Windows 10 (21H2)
# More Information
Click on each to get a better understanding of osTicket features.
+ [Roles](https://docs.osticket.com/en/latest/Admin/Agents/Roles.html)
+ [Departments](https://docs.osticket.com/en/latest/Admin/Agents/Departments.html)
+ [Teams](https://docs.osticket.com/en/latest/Admin/Agents/Teams.html)
+ [Agents](https://docs.osticket.com/en/latest/Admin/Agents/Agents.html)
+ [User Directory](https://docs.osticket.com/en/latest/Agent/Users/User%20Directory.html)
+ [Service Level Agreement (SLA)](https://docs.osticket.com/en/latest/Admin/Manage/SLA%20Plans.html)
# Configuration Steps
Open osTicket and login with the credentials you created during installation. 

<img width="770" alt="SS1" src="https://github.com/user-attachments/assets/13dba6f7-0365-4137-b8ff-40264ceb9c8a" />
<img width="862" alt="SS2" src="https://github.com/user-attachments/assets/2635301b-7a96-40e1-ab3e-3fdaf8a8c59b" />

From within the Admin panel, navigate to Agents > Roles > Add New Role. It will be named "SupremeAdmin". In the Permissions tab, check every box under the "Tickets", Tasks", "Knowledgebase" sections.

<img width="833" alt="SS3" src="https://github.com/user-attachments/assets/cfbf8510-5ed9-4a70-b828-23a15997719e" />
<img width="763" alt="SS4" src="https://github.com/user-attachments/assets/d0388af3-6151-4b05-9c91-5b27ff1303c8" />

Now we will configure the departments in our organization. While still in the Admin Panel, Agents > Departments > Add New Department. Name this department "System Administrators". 

<img width="855" alt="SS5" src="https://github.com/user-attachments/assets/15b9128f-3cc1-48fb-84cf-107184b6e586" />

Next, we'll configure Teams. In the Admin Panel, Agents > Teams > Add New Team and name it "Level II Support". Go to the Members tab and add yourself (the admin account) and create the team. After finishing that, we'll adjust permissions for ticket creation. Go to Settings then Users. Uncheck the box "Require registration and login to create tickets" and save changes.

<img width="821" alt="SS7" src="https://github.com/user-attachments/assets/f6525feb-8db9-4968-a206-9d73ca1afb09" />

Now we will configure our 2 agents that will be completing support tickets. Under the Agents tab select "Add New Agents" and enter the following information for the Agents:
+ Agent 1
  + Name: Ken Jay
  + Email: ken.jay@osticket.com
  + Username: ken.jay
+ Agent 2
  + Name: Barbie Jay
  + Email: barbie.jay@osticket.com
  + Username: barbie.jay
Ensure that you uncheck the "send agent a password reset email" and "require password change on next logon" boxes when setting the password. This is good practice in a real-world scenario but for training purposes we will not be using these security features.

<img width="755" alt="SS8" src="https://github.com/user-attachments/assets/51431729-67ed-4a1f-8cd4-3259021a4c6d" />


After setting the agent password, navigate to the Access tab. Under Primary Department, select "System Administrators" and "SupremeAdmin". Under Extended Access, Select Department > Support > Add > SupremeAdmin. Now navigate to the Team tab and select Level II Support. Finish creating the agent.
*pic of both*
Create another agent named "John Doe". You'll follow the same steps as creating the previous agent but with a few exceptions. Under Primary Department select "Support" and "View Only". 
*pic of both*
Now we'll configure users which are the customers for our organization. While in the Agent Panel, select Users > Add User. We'll create 2 separate users in the system which you can see below:
*pic of barbie@osticket.com user and ken@osticket.com user parameters*
Now we will configure 3 Service Level Agreements (SLA). SLAs provide a certain length of time for tickets to be closed. While in the Admin Panel, navigate to Manage > SLA > Add New SLA Plan. Use the following parameters:
+ Name: SEV-A
+ Grace Period: 1
+ Schedule: 24/7
For the second SLA:
+ Name: SEV-B
+ Grace Period: 4
+ Schedule: 24/7
For the third SLA:
+ SEV-C
+ Grace Period: 8
+ Schedule: Mon-Fri 8am-5pm with U.S. Holidays

Finally, we will now configure the Help Topics. While in the Admin Panel > Manage > Help Topics > Add New Help Topic. The 4 help topics we'll be creating are:
+ Business Critical Outage
+ Personal Computer Issues
+ Equipment Request
+ Password Reset
*pic of adding topics*
Nice! We've successfully configured osTicket. To learn more about the lifecycle of a ticket, follow pt.3 of this tutorial [here](https://github.com/nahjac/osTicket-Ticket-Lifecycle-Examples).
