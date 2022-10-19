
# ACCESS WHEN KEY PAIR IS LOST

#### We will solve the problem of losing the access key pair

Key Pair is used to encrypt and decrypt credentials to the EC2 virtual server.

In case of losing the key pair, we can perform the following steps to assign a new key pair.

1.  In the  **EC2**  interface

-   Select  **AMIs**
-   Select  **Custom Windows AMI**  just created from  **Microsoft Windows Server 2022**  instance

![Key Pair](https://000004.awsstudygroup.com/images/5-AmazonEC2basic/5.4-Keypair/0001-keypair.png?featherlight=false&width=90pc)

2.  **Name**, enter  `Windows Server AMI`

![Key Pair](https://000004.awsstudygroup.com/images/5-AmazonEC2basic/5.4-Keypair/0002-keypair.png?featherlight=false&width=90pc)

3.  In the  **AMI**  selection

-   Select  **AMI from catalog**

![Key Pair](https://000004.awsstudygroup.com/images/5-AmazonEC2basic/5.4-Keypair/0003-keypair.png?featherlight=false&width=90pc)

4.  Next, select  **Instance type**  and select  **Create new key pair**

![Key Pair](https://000004.awsstudygroup.com/images/5-AmazonEC2basic/5.4-Keypair/0004-keypair.png?featherlight=false&width=90pc)

5.  In the  **Create key pair**  interface

-   **Key pair name**, enter  `kp-windows2`
-   **Private key file format**, select  **.pem**
-   Select  **Create key pair**

![Key Pair](https://000004.awsstudygroup.com/images/5-AmazonEC2basic/5.4-Keypair/0005-keypair.png?featherlight=false&width=90pc)

6.  Then we configure the network for the new instance. In  **Network settings**

-   **VPC**, select  **windows-vpc**
-   **Subnet**, select  **public subnet**
-   **Auto-assign public IP**, select  **Enable**
-   In the  **Firewall (security group)**  section, select  **Select existing security group**
-   Select  **Windows-SG**

![Key Pair](https://000004.awsstudygroup.com/images/5-AmazonEC2basic/5.4-Keypair/0006-keypair.png?featherlight=false&width=90pc)

7.  Double check and select  **Launch instance**

![Key Pair](https://000004.awsstudygroup.com/images/5-AmazonEC2basic/5.4-Keypair/0007-keypair.png?featherlight=false&width=90pc)

8.  Finish creating a new instance, select  **View all instance**  to see details about the instance

![Key Pair](https://000004.awsstudygroup.com/images/5-AmazonEC2basic/5.4-Keypair/0008-keypair.png?featherlight=false&width=90pc)

9.  Wait about 5 minutes after initialization,  **Status check**  changes to  **2/2 checks passed**.

![Key Pair](https://000004.awsstudygroup.com/images/5-AmazonEC2basic/5.4-Keypair/0009-keypair.png?featherlight=false&width=90pc)
