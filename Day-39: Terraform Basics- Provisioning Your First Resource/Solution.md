## Now, let's solve the challenge!

# Prerequisites:
1. AWS account
2. AWS CLI installed and configure (to install; refer the official AWS documentation)
3. IAM user for AWS CLI usage with required permissions


Steps:
1. Verify that AWS CLI is installed:<br>
   ```aws --version```<br>
   <img width="632" height="71" alt="image" src="https://github.com/user-attachments/assets/4f05d02a-918b-4ff9-a234-e0593f7f158a" />

2. Configure the AWS CLI:<br>
   ```aws configure```
   <img width="878" height="133" alt="image" src="https://github.com/user-attachments/assets/d25bd531-23d9-4fb9-b86a-4b9e69c4f991" />

3. Verify whether the terraform is installed or not<br>
   ```terraform version```

4. For this particular challenge, I will use Terraform to create a Simple Storage Bucket(S3 bucket)<br>
   - Create a project directory<br>
     ```mkdir terraform-basics```<br>
     ```cd terraform-basics```<br>

5. Create a file named: ```main.tf``` and paste the content from the file provided.
   
6. Initialize terraform:<br>
   ```terraform init```<br>
   <img width="980" height="547" alt="image" src="https://github.com/user-attachments/assets/3cd05176-d620-4089-bcad-ee1404cdfbf2" />

7. Validate the configurations:<br>
   ```terraform validate```<br>
   <img width="795" height="295" alt="image" src="https://github.com/user-attachments/assets/fc606bc9-7c13-4ad7-aaa7-10ceb5e2ba68" />

8. Check the execution plan:<br>
   ```terraform plan```<br>
   <img width="987" height="939" alt="image" src="https://github.com/user-attachments/assets/9529300c-c809-4482-bfd1-10ad33841ff0" />
   <img width="1001" height="761" alt="image" src="https://github.com/user-attachments/assets/84e1a204-634b-4fe9-9df2-abb2197b51f2" />

9. Apply this plan to create the bucket: <br>
   ```terraform apply```<br>
   <img width="1087" height="412" alt="image" src="https://github.com/user-attachments/assets/4f0cf5f6-6c1b-4e6f-9545-9e701a6070cd" />

10. Verify that the S3 bucket is created
    - 1st way: Through CLI<br>
      ```aws s3 ls```<br>
      <img width="643" height="71" alt="image" src="https://github.com/user-attachments/assets/51638b64-98c3-4a5b-8fa5-e24dd3a69ea1" />

    - 2nd way: Manually check by navigating to the AWS account
      <img width="1015" height="325" alt="image" src="https://github.com/user-attachments/assets/6a0207af-50de-461b-a825-11e94652e95f" />

11. Now, cleanup the things<br>
    ```terraform destroy```
    <img width="941" height="306" alt="image" src="https://github.com/user-attachments/assets/b06261a0-6379-4d9a-819d-7279138fb7de" />

   
   
