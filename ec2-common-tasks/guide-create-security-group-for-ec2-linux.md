
# CREATE SECURITY GROUP FOR EC2 LINUX

#### Create Security Group for Linux Instance

1.  Go to  [AWS Management Console](https://aws.amazon.com/console/)

-   Find and select  **VPC**
-   Select  **Security Group**

![create security group for linux instance](https://000004.awsstudygroup.com/images/2-Prerequiste/2.3-createsecuritygrouplinux/0001-createsecuritygrouplinux.png?featherlight=false&width=90pc)

2.  In the  **Create security group**  interface

-   **Security group name**, enter  `Linux-SG`
-   **Description**, enter  `Security group for Linux instance`
-   **VPC**, select  **linux-vpc**  just created

![create security group for linux instance](https://000004.awsstudygroup.com/images/2-Prerequiste/2.3-createsecuritygrouplinux/0002-createsecuritygrouplinux.png?featherlight=false&width=90pc)

3.  Configure  **Inbound rule**

-   **SSH**, port 22 to connect via PuTTY.
-   **All ICMP-IPv4**
-   **All ICMP-IPv6**
-   **HTTP**, port 80
-   **HTTPS**, port 443
-   **MySQL/Aurora**, port 3306 used for Database MySQL.
-   **Custom TCP**, port 5000 to run Nodejs application

![create security group for linux instance](https://000004.awsstudygroup.com/images/2-Prerequiste/2.3-createsecuritygrouplinux/0003-createsecuritygrouplinux.png?featherlight=false&width=90pc)

4.  Configure  **Outbound rules**

-   The tag section fills in the key and value
-   Select  **Create security group**
