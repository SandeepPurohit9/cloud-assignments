# Module-2: EC2 Assignment - 1
1. Create an Instance in us-east-1 (N. Virginia) region with an Ubuntu OS and install Nginx for
making them web servers
2. Change the default website with a hello world page


===============================================


## Solution 🔥

1. Open the Amazon EC2 console at https://console.aws.amazon.com/ec2/.
2.  In the navigation bar at the top of the screen,Select a Region in which to launch the instance.we will choose US East (N.Virginia)  us-east-1.
3. From the Amazon EC2 console dashboard, choose Launch instance.
4. Specify an instance name & additional tags is optional.
5. Under Application and OS Images (Amazon Machine Image), choose Quick Start, and then choose the Ubuntu, SSD Volume Type for your instance.
6. For Instance type, select the instance type for the instance.use Amazon EC2 under the Free Tier by selecting the t2.micro instance type.
7. For Key pair name, choose proceed without key-pair, as we can use aws console for our use case.
8.  Configure the networking settings, select create security group & enable ssh & http traffic from anywhere(just for our use case) 
9. Configure storage for the ec2-instance, 8 gib would be fine for our use case.
10. In advanced settings , add following commands in User data to be executed 
```
#!/bin/bash
sudo apt update -y
sudo apt install nginx -y
sudo systemctl enable nginx
cd /var/www/html
echo "<html><h1>Congratulations! Hello world on $(hostname) an Amazon EC2 instance.</h1></html>" > index.html 
```
Keep all other settings to default and choose Launch instance.

11. Click the Instance ID of the launched instance.
12. Select the launched instance and look for Public IPv4 address and Public IPv4 DNS within Details.
13. Once instance state shows running & status passed, visit Public IPv4 DNS or Public IPv4 address to check nginx welcome page


===============================================

## Troubleshooting / issues 🧑🏻‍💻

- installing nginx via script 
- checking user data script logs