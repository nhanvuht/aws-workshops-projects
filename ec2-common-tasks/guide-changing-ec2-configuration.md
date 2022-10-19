
# CHANGING EC2 CONFIGURATION

#### Change  **EC2 Instance Type**

#### Overview

-   Configuration of Amazon EC2 is not optional, but configuration choice through the selection of EC2 Instance types.

Instance type determines the following factors:

-   CPU (Intel / AMD / ARM (Gaviton 1/2/3) / GPU
-   Memory
-   Network
-   Storage

#### Content

1.  Go to  [AWS Management Console](https://aws.amazon.com/console/)

-   Find  **EC2**
-   Select  **EC2**
-   Select  **Instances**
-   Select  **Windows-instance**
-   Select  **Instance state**
-   Select  **Stop instance**

To change the instance type, we have to stop the instance

![Change instance type](https://000004.awsstudygroup.com/images/5-AmazonEC2basic/5.1-changeconfigureec2/0001-changeconfigureec2.png?featherlight=false&width=90pc)

2.  Authenticate  **Stop instance**  by selecting  **Stop**

![Change instance type](https://000004.awsstudygroup.com/images/5-AmazonEC2basic/5.1-changeconfigureec2/0002-changeconfigureec2.png?featherlight=false&width=90pc)

3.  Change the instance type

-   Select  **Windows-instance**
-   Check  **Instance state**  is  **Stopped**
-   Select  **Actions**
-   Select  **Instance settings**
-   Select  **Change instance type**

![Change instance type](https://000004.awsstudygroup.com/images/5-AmazonEC2basic/5.1-changeconfigureec2/0003-changeconfigureec2.png?featherlight=false&width=90pc)

4.  In the  **Change instance type**  interface

-   Change the type from  **t2.micro**  to  **t3.medium**
-   **Instance type**, select  **t3.medium**
-   Select  **Apply**

![Change instance type](https://000004.awsstudygroup.com/images/5-AmazonEC2basic/5.1-changeconfigureec2/0004-changeconfigureec2.png?featherlight=false&width=90pc)

5.  After changing instance type

-   Select  **Windows-instance**
-   Check  **instance type**
-   Select  **Instance state**
-   Select  **Start instance**

![Change instance type](https://000004.awsstudygroup.com/images/5-AmazonEC2basic/5.1-changeconfigureec2/0005-changeconfigureec2.png?featherlight=false&width=90pc)

6.  Wait about 5 minutes,  **Status check**  changes to  **2/2 checks passed**  and  **Instance state**  is  **Running**

![Change instance type](https://000004.awsstudygroup.com/images/5-AmazonEC2basic/5.1-changeconfigureec2/0006-changeconfigureec2.png?featherlight=false&width=90pc)
