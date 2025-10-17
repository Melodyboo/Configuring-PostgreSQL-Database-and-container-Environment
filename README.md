<img width="901" height="345" alt="Screenshot 2025-10-17 093811" src="https://github.com/user-attachments/assets/9c970dcf-acc1-442d-b85f-6b5dffab7fee" /># Configuring-PostgreSQL-Database-and-container-Environment
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
  - set up storage space to be 1cpu and memory= 2Gb
  - verify deployment

  After this go to the resources copy the already made url and paste it on your browser to see the display

  ISSUES I ENCOUNTERED
  at first i used 0.5vcpu and Memory 0.1 and i was having error then i increased the memory space and it worked
  
*CONFIGURE POSTGRESQL DATABASE*
STEP 1
open azure click on New Azure Database for PostgreSQL flexible server
<img width="649" height="519" alt="Screenshot 2025-10-17 090755" src="https://github.com/user-attachments/assets/4672e36f-d823-4217-84fb-90e73ba8a7e9" />

STEP 2
-input the resources 
-choose the region that is available ( i used East US)
-the load type is production 
-compute + Storage: i used Burstable, B2s
2 vCores, 4 GiB RAM, 128 GiB storage, P10 (500 IOPS) since the estimated price is low
<img width="901" height="345" alt="Screenshot 2025-10-17 093811" src="https://github.com/user-attachments/assets/e1110aa8-8e7b-4592-af60-aafae519591e" />

-Authentication method that will support the accessing this PostgreSQL server 
;PostgreSQL authentication only: this request putting the adminstration login and password
