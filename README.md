

*CREATE DATABASE*

STEP 1
-Click go to resources 
- from the menu click settings
- database
- <img width="1120" height="360" alt="Screenshot 2025-10-18 095820" src="https://github.com/user-attachments/assets/9f4bbbfd-9db3-4b70-9e38-15c8ece5adec" />

step 2
from the database you will see other database that was created already
<img width="774" height="197" alt="Screenshot 2025-10-18 101217" src="https://github.com/user-attachments/assets/ff6e8082-09c4-4469-ac01-44d4e23871c6" />

i added mine which is demo_db 
<img width="511" height="241" alt="Screenshot 2025-10-18 101628" src="https://github.com/user-attachments/assets/d3fb976b-5f5d-4e48-bfb6-e2b555da0c05" />
and clicked save

demo_db' PostgreSQL database was created
<img width="869" height="253" alt="Screenshot 2025-10-18 101954" src="https://github.com/user-attachments/assets/5c074f31-c54e-498e-99ae-52bcbf1cc52f" />

STEP 3
from the menu click connect
changed the default database to the one i created demo_db
the default database
<img width="623" height="507" alt="Screenshot 2025-10-18 104724" src="https://github.com/user-attachments/assets/f045e89f-7605-4858-af82-b30be4b17cbd" />
the database i created
<img width="454" height="458" alt="Screenshot 2025-10-18 104845" src="https://github.com/user-attachments/assets/74ddee9a-a660-4354-9a3a-ce8c97226aa5" />

STEP 4
after changing the database, it give us different programs connection strings 
<img width="611" height="473" alt="Screenshot 2025-10-18 105507" src="https://github.com/user-attachments/assets/9490eecb-863e-46d3-a8c1-a51a188b2ee7" />

-for my project i'm using Server=texting.postgres.database.azure.com;Database=demo_db;Port=5432;User Id=azureuser;Password={your_password};Ssl Mode=Require;
<img width="426" height="90" alt="Screenshot 2025-10-18 105708" src="https://github.com/user-attachments/assets/f5463196-6ad3-4bad-aafe-726841e01728" />

-inorder to connect to the database we use cloudshell using psql -h texting.postgres.database.azure.com -p 5432 -U azureuser demo_db
<img width="609" height="125" alt="Screenshot 2025-10-18 111251" src="https://github.com/user-attachments/assets/3a8479b8-0ef5-4294-8441-41e1d52b292e" />
<img width="802" height="192" alt="Screenshot 2025-10-18 111856" src="https://github.com/user-attachments/assets/5f2c5da7-d03e-43e0-b01b-e5dbc126379c" />

*CONFIGURE DATABASE*

step 1
from azure create a container app
- after deployment go to resources
- <img width="664" height="473" alt="Screenshot 2025-10-28 195413" src="https://github.com/user-attachments/assets/af1478e7-4c3b-4816-834e-a939a6891e9c" />
- Go to resources
- from the menu you choose revision and replicas and containers
- <img width="658" height="255" alt="Screenshot 2025-10-28 200946" src="https://github.com/user-attachments/assets/b4b4ddc7-904d-4aa6-97e4-e6b9975c1353" />

 - from container we see enivronment variables
 - we click add
 - <img width="740" height="336" alt="Screenshot 2025-10-28 201801" src="https://github.com/user-attachments/assets/ce469b0c-4f2f-464e-bf87-a1a11f8b2de0" />

the other way to add variables is going to security 
- the click secrets
- <img width="954" height="457" alt="Screenshot 2025-10-28 202117" src="https://github.com/user-attachments/assets/4ed56612-fdfd-4460-8a48-6a77ecaa722d" />
add secrets named th secrets (defaultconnection)
<img width="462" height="265" alt="Screenshot 2025-10-28 203016" src="https://github.com/user-attachments/assets/a62f0441-ed64-4252-ba6b-8862f6c4e8fd" />

-go back to containers
-touch environment variables
- click add, the source should be "referenceasecret" and the value should be "defaultconnection" that is the secrets we created
- <img width="865" height="416" alt="Screenshot 2025-10-28 203247" src="https://github.com/user-attachments/assets/b6d53205-db3a-43e3-93e5-c355769a8233" />
- the save as anew revision

  *ARCHITECTURE*
- User: Accesses the web app via browser or device.  
- *Azure Container App*: Runs the web application in a container.  
- *Azure PostgreSQL Flexible Server*: Stores application data.  
- *Azure Container Environment*: Manages networking, scaling, and logs.
- <img width="640" height="327" alt="Screenshot 2025-10-31 111019" src="https://github.com/user-attachments/assets/62be5226-9a0a-455d-b376-dcaa7017f418" />


  Data Flow
1. The user sends a request to the Azure Container App.
2. The app processes requests and interacts with PostgreSQL to store/retrieve data.
3. Azure Container Environment manages scaling, logs, and networking to keep the services running efficiently.


