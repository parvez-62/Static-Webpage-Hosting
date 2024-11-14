# static-web-host
Static Website Deployment with AWS CodePipeline, S3, and CloudFront
This project sets up continuous integration and deployment for a static website using AWS CodePipeline, S3 for storage, CloudFront as the CDN, and GitHub as the source repository.

Setup Instructions
1.Create an S3 Bucket

Go to the S3 console in AWS.

Create a new bucket with a unique name (e.g., my-static-website-bucket).
![Screenshot (20)](https://github.com/user-attachments/assets/3ab800bf-1910-4029-b235-635c3e5ba01b)


Upload a html file in my-static-website-bucket.
image2

-Enable "Static website hosting" in the properties of the bucket

image3

Set Up CloudFront
In the CloudFront console, create a new CloudFront distribution.

WhatsApp Image 2024-11-12 at 7 17 12 PM

Set the origin to your S3 bucket.
image4

Configure the default cache behavior settings as needed.

Set the appropriate bucket policy to allow public read access to the content (adjust if using CloudFront signed URLs).
image5

Check the CloudFront distribution URL.

image7

3. Connect GitHub Repository to CodePipeline
Go to the CodePipeline console.

image8

Create a new pipeline and select GitHub as the source provider.

image9

Authenticate with GitHub and select the repository and branch for the website.

image13

Add an S3 bucket as the deployment destination.

image14

Add S3 as the Deployment Provider
In CodePipeline, add an S3 bucket as the deployment provider.
Point it to the previously created S3 bucket.
Deploy and Verify
Commit changes to the GitHub repository.
CodePipeline will automatically start and deploy the site to the S3 bucket.
Access the deployed website through the CloudFront distribution URL.
Screenshot 2024-11-10 215943

CloudFront caching may delay changes; you can invalidate the cache if needed.
