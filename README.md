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
Open osTicket and login with the credentials you created during installation. From within the Admin panel, navigate to Agents > Roles > Add New Role. It will be named "SupremeAdmin". In the Permissions tab, check every box under the "Tickets", Tasks", "Knowledgebase" sections.
*pic of adding role/permissions*
Now we will configure the departments in our organization. While still in the Admin Panel, Agents > Departments > Add New Department. Name this department "system Administrators". 
*pic of parameters*
Next, we'll configure Teams. In the Admin Panel, Agents > Teams > Add New Team and name it "Level II Support". Go to the Members tab and add yourself (helpdesk) and create the team. After finishing that, we'll adjust permissions for ticket creation. Go to Settings then Users. Uncheck the box "Require registration and login to create tickets" and save changes.
*pic of changing this setting*
Now we will configure our agents that will be completing support tickets. Under the Agents tab select "Add New Agents". 
*pic of both parameters (name: jane doe email: jane.doe@osticket.com username: jane.doe uncheck send agent a pw reset email and require pw change on next logon)*
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
