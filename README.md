# APPLICATION LOAD BALANCER PROJECT.
1)Creating an ALB(Application Load Balancer)steps.
  An application load balancer works at layer 7, i.e., the application layer in the OSI architecture. The application load balancer routes request to the targets, such as EC2 instances, Lambdas, etc.
  For Elastic Container Service, the application load balancer AWS supports dynamic port mapping for containers.
  ![application-load-balancer](https://github.com/user-attachments/assets/336e2f44-8e76-4ac9-a743-cad5c0ae5330)
Steps:
1.Create a VPC according to your requirement and specify the CICR(Classless inter Domain Routing) block.
2.Create an Internet Gateway and attach it to VPC.
3.Create a route table.Here,route table helps to track data packets from source to Destination.
4.Create Subnets that is subnetworks, We can create 2 subnets as it is the project related to load Balancer.
Note:Both the subnets has to be in different Availability Zones.
5.Create an ec2 instance and configure network settings,In the network settings you need to select the Vpc that we have created and subnets we have created.
6.Launch a simple website using the instances.
use these commands for Linux AMI
Sudo yum update -y.
Sudo yum install httpd -y
cd /var/www/html
Sudo vim index.html
//inside the editor you can design your wensite as per your requirements.
<h1>Simple Website-01 for Load Balancer</h1>
//Start the httpd service.
Systemctl start httpd 
7.Create a Target Group and add these 2 instances and Select application Load Balancer.
8.We have Successfully created Application Load Balancer.
