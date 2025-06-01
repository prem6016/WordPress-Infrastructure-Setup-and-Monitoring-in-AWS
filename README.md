# 📘 WordPress Deployment and Monitoring on AWS

This project demonstrates how to **set up, configure, and monitor WordPress instances on AWS** using **CloudFormation**, **Auto Scaling**, **Scheduled Actions**, and **Route53 Health Checks**. It includes a production environment for live blogging and a development environment for testing purposes — aligned with best practices for availability, scalability, and cost-efficiency.

## 🧰 Tools & Technologies
- AWS CloudFormation
- Amazon EC2
- Amazon Linux 2 AMI
- Amazon Machine Image (AMI)
- Auto Scaling Groups (ASG)
- Scheduled Actions
- Route 53 Health Checks
- WordPress CMS

🎯 Project Goals

- Set up a **live WordPress instance** for publishing blogs.
- Create a **dev/test WordPress instance** to trial changes without affecting production.
- Configure the **dev/test instance to run only during business hours (9 AM–6 PM)** using **Auto Scaling Scheduled Actions**.
- Implement **monitoring** of both instances via **Route53 Health Checks**.

🛠️ Implementation Steps

### ✅ Step 1: Deploy Live WordPress Instance

- Use the provided [CloudFormation template](./WordPress_Single_Instance_AmazonLinux2.template) to provision:
  - Amazon EC2 instance (Amazon Linux 2)
  - Apache, PHP, and MySQL setup
  - WordPress installation
- Output: A publicly accessible blog-ready website.

### ✅ Step 2: Create a Custom AMI

- From the configured live WordPress instance, create a custom AMI.
- This AMI will be used for the development/test environment.

### ✅ Step 3: Deploy Dev/Test WordPress Using ASG

- Launch an **Auto Scaling Group (ASG)** with the custom AMI.
- Allows for dynamic provisioning and cost-saving shutdowns.

### ✅ Step 4: Schedule Dev/Test Availability

- Apply **ASG Scheduled Actions** to start and stop the dev/test instance:
  - **Start:** 9:00 AM
  - **Stop:** 6:00 PM
- Ensures cost optimization by running only during business hours.

### ✅ Step 5: Monitor Instances with Route 53

- Configure **Route53 Health Checks** to monitor instance health.
- Optional: Use failover routing policy for high availability.

 📸 Screenshots

See the [`SCREENSHOTS.docx`](./SCREENSHOTS.docx) file for a visual walkthrough of:
- CloudFormation deployment
- AMI creation
- ASG setup
- Scheduling actions
- Health check configuration


📌 Notes
Ensure your AWS user has sufficient IAM permissions.

CloudFormation stack will create resources that may incur costs. Don’t forget to clean up!

Change file paths if you are uploading the template via the Console.

🙋‍♂️ Author
Prem Sarkar
GitHub: prem6016
Email: premsarkardps@gamil.com

