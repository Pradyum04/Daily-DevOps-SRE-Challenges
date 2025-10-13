![WhatsApp Image 2025-10-13 at 17 44 43_eacacdb9](https://github.com/user-attachments/assets/76672d02-6e5b-4112-b168-ae2da55ab247)# Objective:
- Installing Docker
- Running containers
- Building custom images
- Inspecting, troubleshooting, and cleaning up container

  ## Step by step solution:
  1. Install docker:
     - For Windows: 
     - For Mac:
     - For Linux:

  2. Verify it:<br>
     ``` docker --version ```<br>
     ``` docker info ```

  3. After installation, pull and run the NGINX container:<br>
     ```docker pull nginx``` <br>
 
     ![WhatsApp Image 2025-10-13 at 17 42 28_200d7b1a](https://github.com/user-attachments/assets/0ec241c8-af85-4ccd-8c73-c7c0631e116b)

      Run the container in detached mode with port mapping:
     ```docker run -d --name n=my-nginx -p 8080:80 nginx``` <br>
     
       Check if it is running:<br>
     ```docker ps```

     ![WhatsApp Image 2025-10-13 at 17 43 47_508aa24a](https://github.com/user-attachments/assets/e4279666-58e6-4a59-9124-454c6ff237e4)

  4. Next steps is to Inspect and Explore the container: <br>
        To view logs of the running container:
      ```docker logs my-nginx```

       ![WhatsApp Image 2025-10-13 at 17 44 43_9caa6bf8](https://github.com/user-attachments/assets/338abfd5-ad1d-4dbd-82f0-57a6fa938b9c)

        To inspect container details (metadata):
      ```docker inspect my-nginx```

      ![WhatsApp Image 2025-10-13 at 17 46 18_5509d0cf](https://github.com/user-attachments/assets/4a7edd89-da4b-4357-813c-4be93f37fd1b)

 5. Next step is to build a Custom Docker Image:
    - Create a new directory
    - Inside it, add the provided index.html file
    - Create a Dockerfile in the same folder
   
 6. Build your image:<br>
    ```docker build -t my-nginx:custom .```

    ![WhatsApp Image 2025-10-13 at 18 02 23_51c416fa](https://github.com/user-attachments/assets/2a1df383-1dce-4f32-8c52-1795c36e50af)


 8. Run your custom container:<br>
    ```docker run -d --name my-custom-nginx -p 8081:80 my-nginx:custom```

    ![WhatsApp Image 2025-10-13 at 18 04 11_4e3613e6](https://github.com/user-attachments/assets/cfffaa29-f348-494a-a1d0-f0accc00ee24)


 10. Access and test in the browser with the given links<br>

 ![WhatsApp Image 2025-10-13 at 18 07 53_3e7b87bc](https://github.com/user-attachments/assets/a5c31a89-2384-4463-9536-67605b6029e4)

 
 11. We successfully run the webapp using Docker. Now last step is cleanup.
     - Stop and remove containers:<br>

       ```docker stop my-nginx my-custom-nginx```<br>

      ![WhatsApp Image 2025-10-13 at 18 31 56_85973948](https://github.com/user-attachments/assets/3da10015-7bd7-4876-815f-858c3ceb0889) <br>

       ```docker rm my-nginx my-custom-nginx```

 13. Remove the custom image:<br>
     ```docker rmi my-nginx:custom```

     ![WhatsApp Image 2025-10-13 at 18 33 11_a57500b3](https://github.com/user-attachments/assets/19aa474c-5146-445d-a44e-1b8e8f9f3532)








      

