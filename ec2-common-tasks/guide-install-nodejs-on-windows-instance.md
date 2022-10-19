# NODEJS APPLICATION ON EC2 WINDOWS

#### Deploy application on  **Microsoft Windows Server 2022**  instance

-   AWS User Management is built with  **Node.js, Express, Express-Handlebars, and MySQL**
-   We will install  **XAMPP**  on  **Microsoft Windows Server 2022 Base**  to use  **MySQL(MariaDB)**  database.
-   Create database, table, insert item on  **phpMyAdmin**  interface
-   Also install  **Nodejs Runtime Environment**
-   Deploy the application and experience the application’s view, add, delete, edit, and search features. (CRUD)

## INSTALL NODEJS ON WINDOWS INSTANCE

#### Install Nodejs on Microsoft Windows Server 2022 instance

1.  To support running the application we install  [Git](https://gitforwindows.org/)

-   Select  **Download**

![AWS User Management ](https://000004.awsstudygroup.com/images/7-AWSFCJmanagement-windows/7.2-InstallNodejsonwindows/0001-installnodejsinwindowsinstance.png?featherlight=false&width=90pc)

2.  Complete installation of  **Git**

![AWS User Management ](https://000004.awsstudygroup.com/images/7-AWSFCJmanagement-windows/7.2-InstallNodejsonwindows/0002-installnodejsinwindowsinstance.png?featherlight=false&width=90pc)

3.  Test install  **Git**  successful

```
git version

```

![AWS User Management ](https://000004.awsstudygroup.com/images/7-AWSFCJmanagement-windows/7.2-InstallNodejsonwindows/0003-installnodejsinwindowsinstance.png?featherlight=false&width=90pc)

4.  Also, we need to download  **IDE**, in this lab use  [Visual Studio Code](https://code.visualstudio.com/download)

![AWS User Management ](https://000004.awsstudygroup.com/images/7-AWSFCJmanagement-windows/7.2-InstallNodejsonwindows/0004-installnodejsinwindowsinstance.png?featherlight=false&width=90pc)

5.  Install  **[Nodejs](https://nodejs.org/en/download/)**  on Windows instance.

-   Select  **Windows Installer**

![AWS User Management ](https://000004.awsstudygroup.com/images/7-AWSFCJmanagement-windows/7.2-InstallNodejsonwindows/0005-installnodejsinwindowsinstance.png?featherlight=false&width=90pc)

6.  Complete the installation of  **[Nodejs](https://nodejs.org/en/download/)**  on the Windows instance.

![AWS User Management ](https://000004.awsstudygroup.com/images/7-AWSFCJmanagement-windows/7.2-InstallNodejsonwindows/0006-installnodejsinwindowsinstance.png?featherlight=false&width=90pc)

7.  Check  **Nodejs**  installed successfully

```
node -v

```

```
npm -v

```

![AWS User Management ](https://000004.awsstudygroup.com/images/7-AWSFCJmanagement-windows/7.2-InstallNodejsonwindows/0007-installnodejsinwindowsinstance.png?featherlight=false&width=90pc)

8.  Create  **AWSManagement**  folder to store the code repository

![AWS User Management ](https://000004.awsstudygroup.com/images/7-AWSFCJmanagement-windows/7.2-InstallNodejsonwindows/0008-installnodejsinwindowsinstance.png?featherlight=false&width=90pc)

9.  Use the  **git init**  command to initialize a local repo. Then use  **git clone**  to clone the repository code

```
git init

```

```
git clone https://github.com/First-Cloud-Journey/000004-EC2.git

```

![AWS User Management ](https://000004.awsstudygroup.com/images/7-AWSFCJmanagement-windows/7.2-InstallNodejsonwindows/0009-installnodejsinwindowsinstance.png?featherlight=false&width=90pc)

10.  Move to  **000004-EC2**  folder

```
cd 000004-EC2

```

![AWS User Management ](https://000004.awsstudygroup.com/images/7-AWSFCJmanagement-windows/7.2-InstallNodejsonwindows/00010-installnodejsinwindowsinstance.png?featherlight=false&width=90pc)
