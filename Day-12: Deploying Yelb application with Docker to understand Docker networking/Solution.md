<img width="1919" height="972" alt="image" src="https://github.com/user-attachments/assets/ab5716e2-33b1-4ddc-90b5-62142b058e01" />Let's solve this challenge to learn Docker Networking!

# Steps to solve this challenges

1. Create a Docker Network
   -Start by creating a user-defined bridge network for container communication.<br>
   -- Why: user-defined bridge gives automatic DNS resolution (container-name → IP) and isolation.<br>
   ```docker network create yelb-network```

  <img width="802" height="57" alt="image" src="https://github.com/user-attachments/assets/040d5370-36ab-4ad4-8910-03d5d37a5734" />

  - Verify it:
    ```docker network ls```<br>
    ```docker network inspect yelb-network```<br>

    <img width="934" height="965" alt="image" src="https://github.com/user-attachments/assets/1a227e13-823d-4eaf-8192-40155d0a018d" />

2. Run the services on by one (through basic run commands):
   Services to be run: i. Redis(cache)
                       ii. Postgres (Yelb DB image)
                       iii. appserver
                       iv. UI
  (All these services to be connected in ```yelb-network```)

  - Redis (cache)
    ```docker run -d --name redis-server --network yelb-network -p 6379:6379 redis:4.0.2```<br>

    <img width="946" height="326" alt="image" src="https://github.com/user-attachments/assets/a8e8900b-1cf7-4d2c-b2a0-1fedb4958acc" />

  - Yelb DB (Postgre prepackaged Image)
    ```docker run -d --name yelb-db --network yelb-network -p 5432:5432 mreferre/yelb-db:0.6```

    <img width="935" height="539" alt="image" src="https://github.com/user-attachments/assets/9c60c6d1-3de2-4b12-bfc8-f4c16abcc940" />

  - Yelb appserver
    ```docker run -d --name yelb-appserver --network yelb-network -p 4567:4567 -e RACK_ENV=test mreferre/yelb-appserver:0.7```

    <img width="949" height="660" alt="image" src="https://github.com/user-attachments/assets/8c4e2960-87ec-4845-a451-d33e6a0568e0" />

  - Yelb UI (frontend)
    ```docker run -d --name yelb-ui --network yelb-network -p 8080:80 -e UI_ENV=test mreferre/yelb-ui:0.10```

    <img width="936" height="376" alt="image" src="https://github.com/user-attachments/assets/daa6a7c2-0016-447b-ac8d-1af0290997aa" />

3. After this verify that all the containers are running:<br>
```docker ps```

<img width="1903" height="212" alt="image" src="https://github.com/user-attachments/assets/1469b639-0fe1-4501-83c7-39c89c6bc4de" />

- Open the ```http://localhost:8080/``` for checking the UI in browser

<img width="1918" height="972" alt="image" src="https://github.com/user-attachments/assets/410ae0af-a5b5-4160-acd0-7439f734881b" />

  Interact with the UI (view items, vote, etc.). If UI loads and actions work, services are talking.

- Inspect network connectivity from inside a container
``` # Exec a shell into the appserver (if image has sh or bash)```
```docker exec -it yelb-appserver sh```
```# Inside container:```
```ping -c 3 redis-server    # may require ping available; busybox images often allow ping```
```# to test HTTP endpoints you can use curl (if installed):```
```curl http://yelb-db:5432   # HTTP here may fail since DB is not HTTP; use other appropriate checks```
```exit```

- ```docker network inspect yelb-network``` to see connected containers:<br>

<img width="1223" height="971" alt="image" src="https://github.com/user-attachments/assets/ab3f11fc-74af-4d08-85f5-6594719b62a4" />

##What is all the containers are removed??
--> Data persists in volumes

4. Make Redis & Postgres persistent (volumes)


  





    




