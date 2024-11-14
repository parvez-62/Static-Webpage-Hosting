
# Static Website Deployment with AWS CodePipeline, S3, and CloudFront


**This project sets up continuous integration and deployment for a static website using AWS CodePipeline, S3 for storage, CloudFront as the CDN, and GitHub as the source repository.**

**Setup Instructions**

1.Create an S3 Bucket

**.** Go to the S3 console in AWS.

-Create a new bucket with a unique name (e.g., my-static-website-bucket).


![Screenshot (20)](https://github.com/user-attachments/assets/3ab800bf-1910-4029-b235-635c3e5ba01b)


-Upload a html file in my-static-website-bucket.

![Screenshot (21)](https://github.com/user-attachments/assets/5cd281a0-fd27-491d-b09a-371a9f36f8e4)


-Enable "Static website hosting" in the properties of the bucket

![image](https://github.com/user-attachments/assets/bfa2c44b-3aa1-4b0d-9c8b-a3f465cf72ab)


**.**Set Up CloudFront


-In the CloudFront console, create a new CloudFront distribution.

![image](https://github.com/user-attachments/assets/1d5de15e-4d1e-4a50-9619-32f81e6c16ef)

-Set the origin to your S3 bucket.

![image](https://github.com/user-attachments/assets/b1a855c6-51f5-4ef8-aecc-054afeb242ff)


-Configure the default cache behavior settings as needed.

-Set the appropriate bucket policy to allow public read access to the content (adjust if using CloudFront signed URLs).
![image](https://github.com/user-attachments/assets/d1b3011c-9670-450c-8a0d-4e11309ace54)



-Check the CloudFront distribution URL.

![image](https://github.com/user-attachments/assets/e672a7bc-a907-470c-8cba-d7db6c18ea44)


3. Connect GitHub Repository to CodePipeline
Go to the CodePipeline console.

![image](https://github.com/user-attachments/assets/0ef811c2-be75-49d2-b529-fc8169fb6ffc)


-Create a new pipeline and select GitHub as the source provider.

![image](https://github.com/user-attachments/assets/65cc283b-d000-451b-91e0-3e14bb42740f)


-Authenticate with GitHub and select the repository and branch for the website.

![image](https://github.com/user-attachments/assets/03cc353e-071d-4e34-9381-70782378d032)


-Add an S3 bucket as the deployment destination.

![image](https://github.com/user-attachments/assets/46741196-7c9d-42af-ad53-d88441a97e73)


-Add S3 as the Deployment Provider

-In CodePipeline, add an S3 bucket as the deployment provider.

-Point it to the previously created S3 bucket.

-Deploy and Verify


![Screenshot (32)](https://github.com/user-attachments/assets/da173580-734a-4de8-9b63-d2fee246e969)



-Commit changes to the GitHub repository.


![Screenshot (34)](https://github.com/user-attachments/assets/ce78a743-140c-487c-ba32-89e90db6b37c)


-CodePipeline will automatically start and deploy the site to the S3 bucket.

-Access the deployed website through the CloudFront distribution URL.

![Screenshot (36)](https://github.com/user-attachments/assets/5f270093-baaf-4971-919b-41c7a2e01db2)


CloudFront caching may delay changes; you can invalidate the cache if needed.
