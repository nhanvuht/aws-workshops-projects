# NODEJS APPLICATION ON EC2 WINDOWS

#### Deploy application on  **Microsoft Windows Server 2022**  instance

-   AWS User Management is built with  **Node.js, Express, Express-Handlebars, and MySQL**
-   We will install  **XAMPP**  on  **Microsoft Windows Server 2022 Base**  to use  **MySQL(MariaDB)**  database.
-   Create database, table, insert item on  **phpMyAdmin**  interface
-   Also install  **Nodejs Runtime Environment**
-   Deploy the application and experience the application’s view, add, delete, edit, and search features. (CRUD)

## INSTALL XAMPP ON WINDOWS INSTANCE

#### Install XAMPP on Microsoft Windows Server 2022 Base instance

**XAMPP**  works based on the integration of 5 main software,  **Cross-Platform (X), Apache (A), MariaDB (M), PHP (P) and Perl (P)**, so The name XAMPP is also an abbreviation of the first letters of this 5 software.

In the lab using MySQL / MariaDB: In MySQL, XAMPP contains one of the most popular relational database management systems in the world. Combined with Apache Web Server and the PHP programming language, MySQL provides data storage capabilities for Web services. Current versions of XAMPP have replaced MySQL with MariaDB (a fork of the community-developed MySQL project, made by the original developers).

1.  In the  **EC2**  interface

-   Select  **Instances**
-   Select  **Windows-instance**
-   View configuration details  **Windows-instance**

![AWS User Management ](https://000004.awsstudygroup.com/images/7-AWSFCJmanagement-windows/7.1-Xampponwindows/0001-xampponwindowsinstance.png?featherlight=false&width=90pc)

2.  Go to the interface ***Remote Desktop Connection**  after connecting  **Microsoft Windows Server 2022**  instance

In case, you are not connected to  **Microsoft Windows Server 2022**  instance, you can repeat step 3.2. Connect Windows instance

![AWS User Management ](https://000004.awsstudygroup.com/images/7-AWSFCJmanagement-windows/7.1-Xampponwindows/0002-xampponwindowsinstance.png?featherlight=false&width=90pc)

3.  Install  **XAMPP**  at  [XAMPP](https://www.apachefriends.org/download.html)

![AWS User Management ](https://000004.awsstudygroup.com/images/7-AWSFCJmanagement-windows/7.1-Xampponwindows/0003-xampponwindowsinstance.png?featherlight=false&width=90pc)

4.  Go to  **User Account Control Settings**  select low level and select  **OK**  to easily install  **XAMPP**

![AWS User Management ](https://000004.awsstudygroup.com/images/7-AWSFCJmanagement-windows/7.1-Xampponwindows/0004-xampponwindowsinstance.png?featherlight=false&width=90pc)

5.  Complete the installation steps  **XAMPP**

![AWS User Management ](https://000004.awsstudygroup.com/images/7-AWSFCJmanagement-windows/7.1-Xampponwindows/0005-xampponwindowsinstance.png?featherlight=false&width=90pc)

6.  Select  **Finish**  to finish

![AWS User Management ](https://000004.awsstudygroup.com/images/7-AWSFCJmanagement-windows/7.1-Xampponwindows/0006-xampponwindowsinstance.png?featherlight=false&width=90pc)

7.  In the  **XAMPP Control Panel**  interface

-   Select  **Start**  Apache server running port 80 or 443
-   Select  **Start**  MySQL database with port 3306

![AWS User Management ](https://000004.awsstudygroup.com/images/7-AWSFCJmanagement-windows/7.1-Xampponwindows/0007-xampponwindowsinstance.png?featherlight=false&width=90pc)

8.  Go to  [http://localhost/phpmyadmin](http://localhost/phpmyadmin/).

We perform login with root information,  **user name**  is root and  **password**  is blank. Then select  **Log in**

-   Create a new database by selecting  **New**

![AWS User Management ](https://000004.awsstudygroup.com/images/7-AWSFCJmanagement-windows/7.1-Xampponwindows/0008-xampponwindowsinstance.png?featherlight=false&width=90pc)

9.  Perform database configuration

-   **Database name**, enter  `awsuser`
-   Select  **Create**

![AWS User Management ](https://000004.awsstudygroup.com/images/7-AWSFCJmanagement-windows/7.1-Xampponwindows/0009-xampponwindowsinstance.png?featherlight=false&width=90pc)

10.  Complete database creation

![AWS User Management ](https://000004.awsstudygroup.com/images/7-AWSFCJmanagement-windows/7.1-Xampponwindows/00010-xampponwindowsinstance.png?featherlight=false&width=90pc)

11.  Execute  **SQL Schema**  by

-   Select the newly created database
-   Select  **SQL**  Enter the following SQL query code:

```
CREATE TABLE `awsuser`.`user` ( `id` INT NOT NULL AUTO_INCREMENT , `first_name` VARCHAR(45) NOT NULL , `last_name` VARCHAR(45) NOT NULL , `email` VARCHAR(45) NOT NULL , `phone` VARCHAR(45) NOT NULL , `comments` TEXT NOT NULL , `status` VARCHAR(10) NOT NULL DEFAULT 'active' , PRIMARY KEY (`id`)) ENGINE = InnoDB;

```

-   Select  **Format**
-   Select  **Go**

![AWS User Management ](https://000004.awsstudygroup.com/images/7-AWSFCJmanagement-windows/7.1-Xampponwindows/00011-xampponwindowsinstance.png?featherlight=false&width=90pc)
