# Configuring-PostgreSQL-Database-and-container-Environment
Configuring PostgreSQL Database and container Environment
***objective****
*Deploy an application using container app Service using Azure*

Steps To depoly the application
CREATE A RESOURCE GROUPS
in azure portal
-open the resource groups
- click create
- choose a name a name and region ( East us2)

  CREATE A CONTAINER APP ENIVROMENT
  - open the container app
  - click container app
  - put the resources group
  - create a new container app enivronment
  - enable ingress made it external
  - target port: 3000
  - set up stora<img width="729" height="393" alt="Screenshot 2025-07-13 172025" src="https://github.com/user-attachments/assets/7015da56-e9b4-44fc-ad33-c96a2920a5f6" />
ge space to be 1cpu and memory= 2Gb
  - verify deployment

  After this go to the resources copy the already made url and paste it on your browser to see the display

  ISSUES I ENCOUNTERED
  at first i used 0.5vcpu and Memory 0.1 and i was having error then i increased the memory space and it worked
  
