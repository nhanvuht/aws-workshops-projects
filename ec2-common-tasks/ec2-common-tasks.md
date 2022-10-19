# Common tasks on EC2

This project will perform common tasks on EC2 as the following:
1. Build basic network setting for EC2 instances
2. Create, launch Microsoft Windows Server 2022 instance. Test connection
3. Create, launch Amazon Linux 2 instances. Test connection
4. Change EC2 configuration
5. Create snapshot for EC2
6. Build optional/customized AMI
7. Access when key pair is lost
8. NODEJS APPLICATION ON EC2 LINUX
9. - Install LAMP web server on Amazon Linux 2
10. - Install Nodejs Runtime Environment on Amazon Linux 2
11. - Deploy CRUD Application on Amazon Linux 2
12. NODEJS APPLICATION ON EC2 WINDOWS
13. - Install XAMPP on Microsoft Windows Server 2022 Base instance
14. - Install Nodejs Runtime Environment on Microsoft Windows Server 
15. - Deploy application on Microsoft Windows Server 2022 instance
16. Clean up built resources

### Basic network setup
 - [ ] Create VPC, public subnet for Linux Instance 
 - [ ] Create VPC, public subnet for Windows Instance
 - [ ] Create Security Group for Linux Instance 
 Inbound rule:
     -   **SSH**, port 22 to connect via PuTTY.
    -   **All ICMP-IPv4**
    -   **All ICMP-IPv6**
    -   **HTTP**, port 80
    -   **HTTPS**, port 443
    -   **MySQL/Aurora**, port 3306 used for Database MySQL.
    -   **Custom TCP**, port 5000 to run Nodejs application
 - [ ] Create Security Group for Windows Instance
  Inbound rule:
    -   **SSH**, port 22
    -   **HTTP**, port 80
    -   **HTTPS**, port 443
    -   **RDP**, port 3389 for connection
    -   **All ICMP-IPv4**
    -   **All ICMP-IPv6**
    -   **Custom TCP**, port 5000 to run Nodejs app
    -   **MYSQL/Aurora**, port 3306 for Database MySQL
































#### Overview

#### Amazon Elastic Compute Cloud ( EC2 )

-   **Amazon EC2**  is like a traditional physical or virtual server. EC2 has fast initialization, strong resource scalability, and flexibility.
-   **Virtual server:**  splits the physical server into many virtual servers, the purpose is to make better use of resources.
-   **Amazon EC2**  can support workloads like web hosting, applications, databases, authentication services, and anything else that a regular server can handle.

#### Amazon Elastic Compute Cloud ( EC2 ) – Instance Type

Configuration of Amazon EC2 is not optional, but configuration choice through selection of EC2 Instance types.

Instance type determines the following factors:

-   CPU (Intel / AMD / ARM (Graviton 1/2/3) / GPU
-   Memory
-   Network
-   Storage

#### Amazon Elastic Compute Cloud ( EC2 ) – AMI / Backup / Key Pair

-   Using  **AMI (Amazon Machine Image)**  can  **provision**  one or more  **EC2 Instances**  at the same time.
-   **AMI**  available from AWS, on  **AWS Market Place**  and  **custom AMI**  created from  **EC2 Instances**.
-   **AMI**  includes  **root OS volumes**,  **AMI**  usage rights specify the AWS account to be used, and  **mapping EBS volumes**  will be created and assigned to EC2 Instances.
-   **EC2 instance**  can be  **backup**  by  **creating snapshot**.
-   **Key pair (public key and private key )**  used to encrypt login information for  **EC2 Instance**


