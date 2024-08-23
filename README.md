goals
The project aims to host a static website on Amazon S3, automate deployment using CircleCI, and secure the site with an SSL certificate using AWS Certificate Manager. Additionally, Amazon CloudFront is used as a CDN to distribute the website globally.
Steps
1. Set Up S3 Bucket:
Log into AWS and navigate to the S3 service.
Create a new bucket with a name corresponding to your domain (e.g., www.yourdomain.com).
Enable static website hosting in the bucket properties and specify the index document (e.g., index.html).
2. Configure CI/CD with CircleCI:
Upload your website code to a GitHub repository.
Create a .circleci directory in your repository and add a config.yml file.
Write a CircleCI configuration to deploy the code to the S3 bucket using the AWS CLI.
3. Set Up CircleCI:
Connect CircleCI to your GitHub account and set up the project.
Add environment variables in CircleCI for AWS access, including AWS_ACCESS_KEY_ID, AWS_SECRET_ACCESS_KEY, AWS_DEFAULT_REGION, and AWS_S3_BUCKET.
4. Request and Validate SSL Certificate:
Use AWS Certificate Manager to request a public SSL certificate for your domain.
Validate the certificate by adding a CNAME record in your DNS provider (e.g., GoDaddy).
5. Set Up CloudFront:
Create a CloudFront distribution and select your S3 bucket as the origin.
Use the SSL certificate obtained from AWS Certificate Manager for HTTPS support.
Configure CloudFront settings, including origin access identity and bucket policy updates.
6. Finalize and Test:
Wait for DNS propagation and CloudFront distribution deployment.
Access your website using the CloudFront domain name or your custom domain to ensure everything is working correctly.
By following these steps, you can efficiently host a static website with automated deployment and secure it with an SSL certificate. This setup leverages AWS services to ensure scalability, security, and global distribution.
