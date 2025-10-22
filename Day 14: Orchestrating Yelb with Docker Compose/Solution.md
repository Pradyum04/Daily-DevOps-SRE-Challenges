## Let's solve this challenge with the following steps:

1. Make a folder ```yelb-compose```, open the terminal and go to this folder using the following commands:<br>
   ```mkdir yelb-compose```<br>
   ```cd yelb-compose```

2. Verify the Docker compose availability<br>
   ```docker compose version```

3. Start all services in detached mode<br>
   ```docker compose up -d```

   <img width="946" height="458" alt="image" src="https://github.com/user-attachments/assets/6a40cc29-2c90-437e-9b09-c2d0a2b95d97" />

4. Now check the status<br>
   ```docker compose ps```

   <img width="1907" height="266" alt="image" src="https://github.com/user-attachments/assets/27a62b53-1a55-4e8a-9be9-dfb70fa607cc" />

5. Check the tail logs:<br>
   ```docker compose logs -f --tail=50```

   <img width="1892" height="957" alt="image" src="https://github.com/user-attachments/assets/a535a286-ec0f-44ed-a5c2-08c35bbaf05d" />
   <img width="1889" height="936" alt="image" src="https://github.com/user-attachments/assets/1d188590-4ba3-4a25-89f7-9ac33f0707e9" />

    you can also check for specific service (for eg: UI)<br>
    ```docker compose logs -f ui```
    <img width="1889" height="936" alt="image" src="https://github.com/user-attachments/assets/1f6992af-c8e8-45f5-be3c-f29fa6457d7f" />

6. Open UI in browser:<br>
   If local: ```http://localhost:8080```<br>
   If EC2: ```http://<EC2_PUBLIC_IP>:8080``` (ensure SG allows port 8080)<br>
You should see Yelb UI and be able to interact (view items, vote).

7. Check the netwroking:<br>
   ```docker network ls```<br>
   ```docker network inspect yelb-compose_yelb-net```

  <img width="676" height="149" alt="image" src="https://github.com/user-attachments/assets/d300d6e8-8acc-4cc1-b5c6-1586f161e97a" />
  <img width="1230" height="970" alt="image" src="https://github.com/user-attachments/assets/9c4e9f14-aeb1-4dde-831c-bdf3f06779b4" />
  <img width="1393" height="694" alt="image" src="https://github.com/user-attachments/assets/275a055c-99f3-4d55-bf3f-52ef9d279ca4" />

8. Verfiy volumes:<br>
   ```docker network ls```<br>
   ```docker network inspect yelb-compose_yelb-net```

   <img width="919" height="201" alt="image" src="https://github.com/user-attachments/assets/933fa367-8186-4904-a3fc-d68fbee37fda" />
   <img width="1247" height="951" alt="image" src="https://github.com/user-attachments/assets/1a45ea6e-11e2-40a5-9099-118acdf98808" />

9. Cleanup:<br>
    ```docker compose down```<br>
    ```docker compose down --volumes```<br>

    <img width="934" height="245" alt="image" src="https://github.com/user-attachments/assets/04a49d26-18f3-4f8b-bd57-6e1d19815127" />
    <img width="927" height="186" alt="image" src="https://github.com/user-attachments/assets/8c03db39-817e-468f-8b8d-afe1ad47d771" />


   
   
