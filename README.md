🌐 Suganya Ravindran: Global Cloud Portfolio Site
Project Summary
This project demonstrates the deployment of a low-latency, highly-available, and secure static website using core Amazon Web Services (AWS) Platform-as-a-Service (PaaS) and Software-as-a-Service (SaaS) offerings.

The primary objective was to deploy a basic HTML/CSS portfolio and serve it globally with maximum performance and HTTPS security while minimizing operational overhead.

🚀 Architecture and Cloud Services
The website follows a modern, serverless static hosting architecture.

Service	Purpose in Architecture	Key Technical Skill
Amazon S3	Origin Storage/Host: Stores all static assets (HTML, CSS). Configured for Static Website Hosting and served as the origin for the CDN.	Lifecycle Management, Bucket Policies (IAM)
Amazon CloudFront	Global Content Delivery Network (CDN): Caches content at over 400 Edge Locations worldwide, ensuring low latency and high availability.	CDN Configuration, SSL/TLS Management
HTTPS/SSL	Security: Automatically provisioned and managed by CloudFront, enforcing secure data transfer between the client and the CDN.	Security Best Practices, Certificate Management
🛠️ Deployment Steps & Technical Deep Dive
The following steps were executed to deploy the site:

1. Code Preparation & Version Control

Created a simple, clean index.html and styles.css file from scratch.

Initialized a local Git repository and pushed all code to a remote GitHub repository (suganya-ravindran/my-cloud-portfolio).

Skill Highlight: Git command-line usage and handling SSH credential conflicts.

2. S3 Bucket Configuration (The Origin)

A new S3 bucket (suganya-portfolio-website-2025) was created in the us-east-1 region.

Static Website Hosting was enabled, setting index.html as the Index Document.

A Bucket Policy was applied to grant s3:GetObject permission to the public, allowing CloudFront (and eventually the public) to retrieve the content.

3. Content Delivery Network (CDN) Setup

An Amazon CloudFront Distribution was created.

The Origin was set to the S3 Website Endpoint (not the S3 bucket ARN).

The Viewer Protocol Policy was configured to Redirect HTTP to HTTPS to enforce secure access.

The Default Root Object was set to index.html.

CloudFront successfully deployed, provisioning a global HTTPS endpoint (e.g., https://dmz2xdriiayne.cloudfront.net).

4. Resource Cleanup (Cloud Best Practices)

To adhere to responsible cloud financial governance, all resources were successfully decommissioned after validation.

The CloudFront Distribution was disabled and then deleted.

The S3 bucket and all objects were deleted.

🔗 Live Site and Validation
The site was live and accessible globally at the following secure endpoint:

https://dmz2xdriiayne.cloudfront.net

(Screenshots of the live site and AWS configuration are available upon request during an interview.)

💡 Next Steps / Future Goals
Custom Domain: Integrate Amazon Route 53 and AWS Certificate Manager (ACM) to host the site on a custom domain (e.g., suganya-portfolio.com).

Infrastructure-as-Code (IaC): Rebuild the entire architecture using Terraform or AWS CloudFormation for automated, repeatable deployment.

Pipeline: Implement an AWS CodePipeline and CodeBuild solution to automate deployment directly from GitHub to S3 and invalidate the CloudFront cache upon every code push.