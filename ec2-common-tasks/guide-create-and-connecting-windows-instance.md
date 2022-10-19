
# CREATE WINDOWS INSTANCE

#### Create Microsoft Windows Server 2022 instance

1.  Go to  [AWS Management Console](https://aws.amazon.com/console/)

-   Find  **EC2**
-   Select  **EC2**

![create windows instance](https://000004.awsstudygroup.com/images/3-Launchwindowsinstance/3.1-createwindowssintance/0001-createwindowsinstance.png?featherlight=false&width=90pc)

2.  In the  **EC2**  interface

-   Select  **Instances**
-   Select  **Launch instances**

![create windows instance](https://000004.awsstudygroup.com/images/3-Launchwindowsinstance/3.1-createwindowssintance/0002-createwindowsinstance.png?featherlight=false&width=90pc)

3.  **Name**, enter  `Windows-instance`

![create windows instance](https://000004.awsstudygroup.com/images/3-Launchwindowsinstance/3.1-createwindowssintance/0003-createwindowsinstance.png?featherlight=false&width=90pc)

4.  In the  **AMI**  selection step

-   Select  **Quick Start**
-   Select  **Windows**
-   **AMI**, select  **Microsoft Windows Server 2022 Base**

![create windows instance](https://000004.awsstudygroup.com/images/3-Launchwindowsinstance/3.1-createwindowssintance/0004-createwindowsinstance.png?featherlight=false&width=90pc)

5.  Select  **Instance type**  and select  **Create new key pair**

![create windows instance](https://000004.awsstudygroup.com/images/3-Launchwindowsinstance/3.1-createwindowssintance/0005-createwindowsinstance.png?featherlight=false&width=90pc)

6.  In the  **Create key pair**  interface

-   **Key pair name**, enter  `kp-windows`
-   **Private key file format**, select  **.pem**
-   Select  **Create key pair**, to create key pair and the key pair is stored on your computer.

![create windows instance](https://000004.awsstudygroup.com/images/3-Launchwindowsinstance/3.1-createwindowssintance/0006-createwindowsinstance.png?featherlight=false&width=90pc)

7.  In the  **Network settings**  section, select  **Edit**  to configure the network for  **instance**

![create windows instance](https://000004.awsstudygroup.com/images/3-Launchwindowsinstance/3.1-createwindowssintance/0007-createwindowsinstance.png?featherlight=false&width=90pc)

8.  Proceed to configure the network for  **instance**

-   **VPC**, select  **windows-vpc**
-   **Subnet**, select  **public subnet**
-   **Auto-assign public IP**, select  **Enable**
-   In the  **Firewall (security groups)**  section, select  **Select existing security group**
-   Select  **Windows-SG**

![create windows instance](https://000004.awsstudygroup.com/images/3-Launchwindowsinstance/3.1-createwindowssintance/0008-createwindowsinstance.png?featherlight=false&width=90pc)

9.  Double check and select  **Launch instance**

![create windows instance](https://000004.awsstudygroup.com/images/3-Launchwindowsinstance/3.1-createwindowssintance/0009-createwindowsinstance.png?featherlight=false&width=90pc)

10.  Successful instance initialization, proceed to view instance details by selecting  **View all instances**

![create windows instance](https://000004.awsstudygroup.com/images/3-Launchwindowsinstance/3.1-createwindowssintance/00010-createwindowsinstance.png?featherlight=false&width=90pc)

11.  Wait for 5 minutes,  **Status check**  will change to  **2/2 checks passed**  and  **Running**  instance status

# CONNECTING WINDOWS INSTANCE

#### Connect from computer to  **Microsoft Windows Server 2022 instance**

1.  In the  **EC2**  interface

-   Select  **Instances**
-   Select  **Windows-instance**
-   select  **Connect**

![connect windows instance](https://000004.awsstudygroup.com/images/3-Launchwindowsinstance/3.2-Connectwindowsinstance/0001-connectwindowsinstance.png?featherlight=false&width=90pc)

2.  In the  **Connect to instance**  interface

-   Select  **RDP Client**  (port 3389)
-   Select  **Download remote desktop file**  to your computer
-   Select  **Get password**  to use  **password**  to connect

![connect windows instance](https://000004.awsstudygroup.com/images/3-Launchwindowsinstance/3.2-Connectwindowsinstance/0002-connectwindowsinstance.png?featherlight=false&width=90pc)

3.  In the  **Get Windows password**  interface

-   Select  **Browse**
-   Select  **kp-windows.pem**  on the local computer
-   Check  **private key**  and select  **Decrypt password**

![connect windows instance](https://000004.awsstudygroup.com/images/3-Launchwindowsinstance/3.2-Connectwindowsinstance/0003-connectwindowsinstance.png?featherlight=false&width=90pc)

4.  After  **Decrypt password**  is successful

-   Copy  **password**  to use the connection via port 3389

![connect windows instance](https://000004.awsstudygroup.com/images/3-Launchwindowsinstance/3.2-Connectwindowsinstance/0004-connectwindowsinstance.png?featherlight=false&width=90pc)

5.  Continue the steps to connect as follows:

-   Open  **remote desktop file**  just downloaded to your device
-   The  **Remote Desktop Connection**  interface appears, select  **Connect**

![connect windows instance](https://000004.awsstudygroup.com/images/3-Launchwindowsinstance/3.2-Connectwindowsinstance/0005-connectwindowsinstance.png?featherlight=false&width=90pc)

6.  Then, we use  **password**  to authenticate the  **Windows Security**  section, select  **OK**

![connect windows instance](https://000004.awsstudygroup.com/images/3-Launchwindowsinstance/3.2-Connectwindowsinstance/0006-connectwindowsinstance.png?featherlight=false&width=90pc)

7.  Select  **Yes**

![connect windows instance](https://000004.awsstudygroup.com/images/3-Launchwindowsinstance/3.2-Connectwindowsinstance/0007-connectwindowsinstance.png?featherlight=false&width=90pc)

8.  After completing the connection to the  **Microsoft Windows Server 2022**  instance, the configuration information of the instance is displayed on the screen.
