
# CREATE LINUX INSTANCE

#### Create 2 Amazon Linux instances

1.  Go to  [AWS Management Console](https://aws.amazon.com/console/)

-   Find  **EC2**
-   Select  **EC2**
-   Select  **Instances**
-   Select  **Launch instances**

![create linux instance](https://000004.awsstudygroup.com/images/4-Launchlinuxinstance/4.1-Createlinuxinstance/0001-createlinuxinstance.png?featherlight=false&width=90pc)

2.  **Name**, enter  `Linux-instance`

![create linux instance](https://000004.awsstudygroup.com/images/4-Launchlinuxinstance/4.1-Createlinuxinstance/0002-createlinuxinstance.png?featherlight=false&width=90pc)

3.  In the  **AMI**  selection step

-   Select  **Quick Start**
-   Select  **Amazon Linux**
-   **AMI**, select  **Amazon Linux 2 AMI**

![create linux instance](https://000004.awsstudygroup.com/images/4-Launchlinuxinstance/4.1-Createlinuxinstance/0003-createlinuxinstance.png?featherlight=false&width=90pc)

4.  Select  **Instance type**  and select  **Create new key pair**

![create linux instance](https://000004.awsstudygroup.com/images/4-Launchlinuxinstance/4.1-Createlinuxinstance/0004-createlinuxinstance.png?featherlight=false&width=90pc)

5.  In the  **Create key pair**  interface

-   **Key pair name**, enter  `kp-linux`
-   **Key pair type**, select  **RSA**
-   **Private key file format**, select  **.pem**
-   Select  **Create key pair**

![create linux instance](https://000004.awsstudygroup.com/images/4-Launchlinuxinstance/4.1-Createlinuxinstance/0005-createlinuxinstance.png?featherlight=false&width=90pc)

6.  Next, we do the network configuration for the instance

-   Select  **Edit**

![create linux instance](https://000004.awsstudygroup.com/images/4-Launchlinuxinstance/4.1-Createlinuxinstance/0006-createlinuxinstance.png?featherlight=false&width=90pc)

7.  In the  **Network settings**  interface, we configure the network for the instance as follows:

-   **VPC**, select  **linux-vpc**
-   **Subnet**, select  **public subnet**
-   **Auto-assign public IP**, select  **Enable**
-   In the  **Firewall (security groups)**  section, select  **Select existing security group**

![create linux instance](https://000004.awsstudygroup.com/images/4-Launchlinuxinstance/4.1-Createlinuxinstance/0007-createlinuxinstance.png?featherlight=false&width=90pc)

8.  Check again and select  **Launch instance**

![create linux instance](https://000004.awsstudygroup.com/images/4-Launchlinuxinstance/4.1-Createlinuxinstance/0008-createlinuxinstance.png?featherlight=false&width=90pc)

9.  Complete instance initialization, proceed to view instance details by selecting  **View all instance**

![create linux instance](https://000004.awsstudygroup.com/images/4-Launchlinuxinstance/4.1-Createlinuxinstance/0009-createlinuxinstance.png?featherlight=false&width=90pc)

10.  Wait about 5 minutes after initialization,  **Status check**  changes to  **2/2 check passed**  and the instance status is  **Running**

![create linux instance](https://000004.awsstudygroup.com/images/4-Launchlinuxinstance/4.1-Createlinuxinstance/00010-createlinuxinstance.png?featherlight=false&width=90pc)


# CONNECTING LINUX INSTANCE

#### Connecting Amazon Linux 2 Using PuTTY

There are several methods for connecting to an EC2 virtual machine running Linux. In this exercise, we will use PuTTY on Windows to connect to a Linux virtual machine.

To facilitate the lab process, you can download the Putty tool attached below and save it to the same path where you downloaded the key pair when creating EC2.

You download  [the SSH and Telnet client itself](https://the.earth.li/~sgtatham/putty/latest/w64/putty.exe)  as  **putty.exe**

You download  [an SCP client, i.e. command-line secure file copy](https://the.earth.li/~sgtatham/putty/latest/w64/pscp.exe)  is  **pscp.exe**

You download  [a RSA and DSA key generation utility](https://the.earth.li/~sgtatham/putty/latest/w64/puttygen.exe)  as  **puttygen.exe**

1.  We proceed to connect Amazon Linux 2 using PuTTY

-   Select  **puttygen.exe**, use load  **private key file**
-   Select  **Load**

![connect linux instance](https://000004.awsstudygroup.com/images/4-Launchlinuxinstance/4.2-Connectlinuxinstance/0001-connectlinuxinstance.png?featherlight=false&width=90pc)

2.  We choose  **kp-linux.pem**  as the  **private key file**  of the  **Amazon Linux 2**  instance

![connect linux instance](https://000004.awsstudygroup.com/images/4-Launchlinuxinstance/4.2-Connectlinuxinstance/0002-connectlinuxinstance.png?featherlight=false&width=90pc)

3.  After successfully importing the key, we choose  **Save private key**  after generation

![connect linux instance](https://000004.awsstudygroup.com/images/4-Launchlinuxinstance/4.2-Connectlinuxinstance/0003-connectlinuxinstance.png?featherlight=false&width=90pc)

4.  Name the key file  **kp-linux**  and select  **Save**

![connect linux instance](https://000004.awsstudygroup.com/images/4-Launchlinuxinstance/4.2-Connectlinuxinstance/0004-connectlinuxinstance.png?featherlight=false&width=90pc)

5.  Go back to the  **EC2**  interface, select  **Linux-instance**, and copy  **Public IPv4 address**

![connect linux instance](https://000004.awsstudygroup.com/images/4-Launchlinuxinstance/4.2-Connectlinuxinstance/0005-connectlinuxinstance.png?featherlight=false&width=90pc)

6.  Next, we use  **putty.exe**  to connect to the  **Amazon Linux 2**  instance via port 22.

-   **Host Name or IP address**, paste  **Public IPv4 address**
-   **Save Sessions**  as  **Linux-Server**
-   Select  **Save**

![connect linux instance](https://000004.awsstudygroup.com/images/4-Launchlinuxinstance/4.2-Connectlinuxinstance/0006-connectlinuxinstance.png?featherlight=false&width=90pc)

7.  We choose  **SSH**

-   Select  **Auth**
-   Select  **Browse**
-   Choose the path  **kp-linux.ppk**
-   Select  **Open**

![connect linux instance](https://000004.awsstudygroup.com/images/4-Launchlinuxinstance/4.2-Connectlinuxinstance/0007-connectlinuxinstance.png?featherlight=false&width=90pc)

8.  Select  **Accept**  to connect

![connect linux instance](https://000004.awsstudygroup.com/images/4-Launchlinuxinstance/4.2-Connectlinuxinstance/0008-connectlinuxinstance.png?featherlight=false&width=90pc)

9.  After connecting we authenticate  **log in**  by entering  **`ec2-user`**

![connect linux instance](https://000004.awsstudygroup.com/images/4-Launchlinuxinstance/4.2-Connectlinuxinstance/0009-connectlinuxinstance.png?featherlight=false&width=90pc)

10.  Complete connection to  **Amazon Linux 2**  instance

![connect linux instance](https://000004.awsstudygroup.com/images/4-Launchlinuxinstance/4.2-Connectlinuxinstance/00010-connectlinuxinstance.png?featherlight=false&width=90pc)

11.  Check the connection again by entering the command  **`ping amazon.com -c5`**

![connect linux instance](https://000004.awsstudygroup.com/images/4-Launchlinuxinstance/4.2-Connectlinuxinstance/00011-connectlinuxinstance.png?featherlight=false&width=90pc)
