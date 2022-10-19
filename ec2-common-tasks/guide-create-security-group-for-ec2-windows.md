
# CREATE SECURITY GROUP FOR EC2 WINDOWS

#### Create Security Group for Windows Instance

1.  Continuing, we create  **Security Group**  for  **Windows Instance**

-   In the interface  **Create security group**
-   **Security group name**, enter  `Windows-SG`
-   **Description**, enter  `Security group for Windows`
-   **VPC**, select  **windows-vpc**

![create security group for windows instance](https://000004.awsstudygroup.com/images/2-Prerequiste/2.4-createsecuritygroupwindows/0001-createsecuritygroupwindows.png?featherlight=false&width=90pc)

2.  Configure  **Inbound rules**

-   **SSH**, port 22
-   **HTTP**, port 80
-   **HTTPS**, port 443
-   **RDP**, port 3389 for connection
-   **All ICMP-IPv4**
-   **All ICMP-IPv6**
-   **Custom TCP**, port 5000 to run Nodejs app
-   **MYSQL/Aurora**, port 3306 for Database MySQL

![create security group for windows instance](https://000004.awsstudygroup.com/images/2-Prerequiste/2.4-createsecuritygroupwindows/0002-createsecuritygroupwindows.png?featherlight=false&width=90pc)

3.  Configure  **Outbound rules**

-   Section  **tag**, enter key and value
-   Select  **Create security group**

![create security group for windows instance](https://000004.awsstudygroup.com/images/2-Prerequiste/2.4-createsecuritygroupwindows/0003-createsecuritygroupwindows.png?featherlight=false&width=90pc)

4.  Finish creating  **Security Group**  for Windows instance

![create security group for windows instance](https://000004.awsstudygroup.com/images/2-Prerequiste/2.4-createsecuritygroupwindows/0004-createsecuritygroupwindows.png?featherlight=false&width=90pc)

5.  Thus, we have finished creating 2  **Security groups**  for instances
