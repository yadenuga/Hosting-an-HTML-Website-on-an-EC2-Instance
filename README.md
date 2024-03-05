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

1.VPC-Proj-2 10.0.0.0/16 (Enabled DNS Hostnames)

2.IGW-Proj-2 (Attached to VPC-Proj-2)

3.NATGW-Proj-2 (Primary Public IP 52.70.81.37, Primary Private IP 10.0.0.214)

4.Public Subnets
PublicSubnetProj2-AZ1 us-east1a 10.0.0.0/24 (Enable auto-assign public IPv4 address)
PublicSubnetProj2-AZ2 us-east1b 10.0.1.0/24 (Enable auto-assign public IPv4 address) 

5.Private Subnets
PrivateSubnetProj2-AZ1 us-east1a 10.0.2.0/24
PrivateSubnetProj2-AZ2 us-east1b 10.0.3.0/24

6.PublicRouteTable-Proj-2
0.0.0.0/0	igw-0de73d34206dc7867	Active	
10.0.0.0/16	local	                Active

7.PublicSubnetProj2 Association
PublicSubnetProj2-AZ1	subnet-017623d5d4a4781c2 10.0.0.0/24	
PublicSubnetProj2-AZ2	subnet-0b4cb1f4a187f5b00 10.0.1.0/24

8.PrivateRouteTable-Proj-2
0.0.0.0/0	nat-080a022356c702058	Active	
10.0.0.0/16	local	                Active

9.PrivateSubnetProj2 Association
PrivateSubnetProj2-AZ1	subnet-0c24cd5d6090da18e 10.0.2.0/24	
PrivateSubnetProj2-AZ2	subnet-0d91cb67e0a18b312 10.0.3.0/24

SCRIPT
#!/bin/bash 
sudo su
yum update -y
yum install httpd git -y
systemctl enable httpd
systemctl start httpd
aws s3 cp s3://aosproject2/xmen-main/xmen-main.zip /var/www/html
cd /var/www/html
unzip xmen-main.zip
mv xmen-main/* /var/www/html
rm -r xmen-main/ xmen-main.zip
systemctl restart httpd

 
 
 


 
 
 



