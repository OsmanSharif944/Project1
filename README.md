# Project1
Launch EC2 Instance and SSH into it
Step 1 : On your console home, click on EC2
Create Key Pair 
Save Key to local directory
Launch EC2 instance
Step 2 : Name EC2 instance 'My instance' - AMI (Linux 2) Select this
Instance type (t2.micro)
Key pair - (Choose the key pair you previously created)
VPC - ( Use Default)
Subnet ( A section of your VPC)
Step 3 : Create Subnet (Launch EC2 inside it )
Create Route table and internet Gateway
Step 4 : Create a Security group
Give it a name and description
Add inbound rules eg. SSH (Source from anywhere) and also HTTP (Source from anywhere)
Step 5 : Configure storage ( Leave Defaut Settings ) 
Step 6 : User Data 
Your user data should install and APACHE web server. Automatically start on boot. Activate web server. Create simple web page.
BASH SCRIPT
#!/bin/bash
yum -y install httpd
systemctl enable httpd
systemctl start httpd
echo ' <html><h1>Hello From Your Web Server!</h1></html>'>
/var/www/html/index.html


HOW TO SSH ON MAC / ON WINDOWS YOU WOULD USE PUTTY

Launch Terminal 
command = cd "Name of your folder that has the private key"
Now you are in the folder where you created the key 
SSH Command = SSH -i "Name of key" ec2-user@publicIPaddress
