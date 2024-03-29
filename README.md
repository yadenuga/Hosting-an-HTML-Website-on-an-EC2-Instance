# Hosting-an-HTML-Website-on-an-EC2-Instance
Hosting an HTML Website on an EC2 Instance
To host an HTML website on an EC2 instance following the provided reference architecture, you can follow these instructions:

Prepare your HTML Website:

Ensure that your HTML website files are ready to be deployed. This includes HTML, CSS, JavaScript, and any other assets required for your website.
Store these files in either your S3 bucket or a GitHub repository.
Set Up EC2 Instance:

Log in to your AWS Management Console.
Navigate to the EC2 service.
Launch a new EC2 instance based on the reference architecture provided. Make sure to choose the appropriate instance type and settings according to your website's requirements.
Configure Security Group:

Create or configure a security group for your EC2 instance to allow inbound traffic on ports 80 (HTTP) and 443 (HTTPS) for web traffic.
Ensure SSH access is restricted to your IP address for security purposes.
Attach an Elastic IP (Optional):

For using your own domain name, attach an Elastic IP address to your EC2 instance to ensure its IP address remains static.
Set Up Auto Scaling Group with Launch Template:

Create a launch template that includes the configuration details of your EC2 instance.
Configure an Auto Scaling Group using this launch template to ensure efficient resource management and scalability.
Configure Route 53:

Navigate to the Route 53 service in AWS Management Console.
Create a hosted zone for your domain name if you haven't already done so.
Create an A record pointing to the Elastic IP address associated with your EC2 instance.
Configure SSL Certificate:

Obtain an SSL certificate either through AWS Certificate Manager (ACM) or another certificate authority.
Associate the SSL certificate with your domain name in the AWS Certificate Manager.
Enable HTTPS:

Install and configure a web server (such as Apache or Nginx) on your EC2 instance.
Configure the webserver to use the SSL certificate you obtained and enable HTTPS.
Redirect HTTP traffic to HTTPS for secure communication.
Deploy Website:

Write a deployment script (e.g., bash script) that can download your website files from the chosen location (S3 bucket or GitHub repository) onto your EC2 instance.
Execute the deployment script on your EC2 instance to deploy the website files.
Test Accessibility:

Access your website using your domain name to ensure it is accessible over HTTPS.

Acceptance Criteria:

Provide a screenshot of the deployed site, demonstrating that it is fully secured with HTTPS.
Include the URL of the deployed site in your Jira comment.
Share the deployment script that you used for hosting the site.
Additional Notes:

Ensure all steps are documented for future reference.
Coordinate with team members for any necessary assistance or collaboration.
Regularly update the status of the story to reflect progress.


![Project#2_01](https://github.com/yadenuga/Hosting-an-HTML-Website-on-an-EC2-Instance/assets/25983732/dd12e3f2-f17a-4cbb-a6dc-7401d5cc5077)

![Project#2_02](https://github.com/yadenuga/Hosting-an-HTML-Website-on-an-EC2-Instance/assets/25983732/cab211f3-ad23-4ea6-985c-436234fb029d)

![Project#2_03](https://github.com/yadenuga/Hosting-an-HTML-Website-on-an-EC2-Instance/assets/25983732/e5eedfe4-a989-4997-b39e-b337a2f17f0e)

![Project#2_04](https://github.com/yadenuga/Hosting-an-HTML-Website-on-an-EC2-Instance/assets/25983732/8296275a-c775-4a40-8241-8344433ceb8b)

![Project#2_05](https://github.com/yadenuga/Hosting-an-HTML-Website-on-an-EC2-Instance/assets/25983732/b2d16294-6016-4101-a467-5b7fb7de6f10)

![Project#2_06](https://github.com/yadenuga/Hosting-an-HTML-Website-on-an-EC2-Instance/assets/25983732/e1323aa1-cf22-43b5-a35c-ac41cfa5d2a9)

![Project#2_07](https://github.com/yadenuga/Hosting-an-HTML-Website-on-an-EC2-Instance/assets/25983732/4411ca98-432a-4c03-ab8a-8e066c32b16d)

![Project#2_08](https://github.com/yadenuga/Hosting-an-HTML-Website-on-an-EC2-Instance/assets/25983732/86f75b7e-88dc-4740-b6ee-de9b38bfa496)

![Project#2_09](https://github.com/yadenuga/Hosting-an-HTML-Website-on-an-EC2-Instance/assets/25983732/852ca785-762e-45af-9d41-3c696c07d049)

![Project#2_10](https://github.com/yadenuga/Hosting-an-HTML-Website-on-an-EC2-Instance/assets/25983732/0beb1d9a-2993-4a3a-89cd-b64d338950f0)





 


 
 
 



