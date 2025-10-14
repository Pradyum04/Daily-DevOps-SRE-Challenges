### Let's solve this challenge and learn the concept of Docker volumes and its application for Persistent application

Step by step solution (Yelb + Docker Volumes)
1. Pre-check and clean up (if any old Yelb containers exists)<br>
   ```docker ps -a```<br>
   ```docker stop yelb-db redis-server```<br>
   ```docker rm yelb-db redis-server```
   
   <img width="907" height="165" alt="image" src="https://github.com/user-attachments/assets/8286dc15-d781-4f75-8740-6b86f23abfeb" />

2. Create named volumes (for PostgreSQL and Redis)
   ```docker volume create pg-data```<br>
   ```docker volume create redis-data```

   Verify: ```docker volume ls```

   <img width="918" height="295" alt="image" src="https://github.com/user-attachments/assets/7297b0a5-307b-41e3-ba22-37588c57c149" />

3. Run the PostgreSQL container with persistent volume<br>
   ```docker run -d --name yelb-db --network yelb-network -v pg-data:/var/lib/postgresql/data -p 5432:5432 mreferre/yelb-db:0.6```
   
   <img width="925" height="534" alt="image" src="https://github.com/user-attachments/assets/bd832cae-f7ec-4b36-9108-94ba9437011b" />

4. Run Redis container with pesistent volume
   ```>docker run -d --name redis-server --network yelb-network -v redis-data:/data -p 6379:6379 redis:4.0.2```

   <img width="931" height="326" alt="image" src="https://github.com/user-attachments/assets/7a91779b-9543-45e8-8741-f04aa71c25c7" />


   
