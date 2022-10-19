# NODEJS APPLICATION ON EC2 LINUX

#### Deploy an AWS User Management Application on Amazon Linux 2

-   AWS User Management is built with Node.js, Express, Express-Handlebars, and MySQL
-   We will install LAMP web server on Amazon Linux 2 to use MySQL database (MariaDB).
-   Create database, table, insert item on  **phpMyAdmin**  interface
-   Also install  **Nodejs Runtime Environment**
-   Deploy the application and experience the application’s view, add, delete, edit, search features.(CRUD)

## INSTALL LAMP to host WordPress website

#### Prepare LAMP Server

After connecting to the  **Amazon Linux 2**  instance, we deploy the application.

1.  To ensure that all your software packages are up to date, execute the following command:

```
sudo yum update -y

```

![Prepare Lamp Server](https://000004.awsstudygroup.com/images/6-AWSFCJmanagement-linux/6.1-Lampserveronec2linux/0001-lampserveronec2linux.png?featherlight=false&width=90pc)

2.  Install  **lamp-mariadb10.2-php7.2 and php7.2**  , use  **Amazon Linux Extras**  to get the latest version of  **LAMP MariaDB**  and  **PHP**  packages for  **Amazon Linux 2**.

```
sudo amazon-linux-extras install -y lamp-mariadb10.2-php7.2 php7.2

```

![Prepare Lamp Server](https://000004.awsstudygroup.com/images/6-AWSFCJmanagement-linux/6.1-Lampserveronec2linux/0002-lampserveronec2linux.png?featherlight=false&width=90pc)

If you receive the error message sudo: amazon-linux-extras: command not found, your instance was not launched with the Amazon Linux 2 AMI (you are probably using the Amazon Linux AMI instead). You can view your Amazon Linux instance with the following command.

```
cat /etc/system-release

```

![Prepare Lamp Server](https://000004.awsstudygroup.com/images/6-AWSFCJmanagement-linux/6.1-Lampserveronec2linux/0003-lampserveronec2linux.png?featherlight=false&width=90pc)

3.  Install the Apache web server, MariaDB and PHP packages.

Use the  **yum install**  command to install multiple software packages and all related dependencies at once.

```
sudo yum install -y httpd mariadb-server

```

![Prepare Lamp Server](https://000004.awsstudygroup.com/images/6-AWSFCJmanagement-linux/6.1-Lampserveronec2linux/0004-lampserveronec2linux.png?featherlight=false&width=90pc)

4.  Start the Apache webserver

```
sudo systemctl start httpd

```

![Prepare Lamp Server](https://000004.awsstudygroup.com/images/6-AWSFCJmanagement-linux/6.1-Lampserveronec2linux/0005-lampserveronec2linux.png?featherlight=false&width=90pc)

5.  Use the systemctl command to configure the Apache webserver to start at every system boot.

```
sudo systemctl enable httpd

```

![Prepare Lamp Server](https://000004.awsstudygroup.com/images/6-AWSFCJmanagement-linux/6.1-Lampserveronec2linux/0006-lampserveronec2linux.png?featherlight=false&width=90pc)

6.  You can verify that httpd is on by running the following command:

```
sudo systemctl is-enabled httpd

```

![Prepare Lamp Server](https://000004.awsstudygroup.com/images/6-AWSFCJmanagement-linux/6.1-Lampserveronec2linux/0007-lampserveronec2linux.png?featherlight=false&width=90pc)

7.  In the  **EC2**  interface

-   Select  **Instances**
-   Select  **Linux-instance**
-   Copy  **Public IPv4 address**

![Prepare Lamp Server](https://000004.awsstudygroup.com/images/6-AWSFCJmanagement-linux/6.1-Lampserveronec2linux/0008-lampserveronec2linux.png?featherlight=false&width=90pc)

8.  Paste  **Public IPv4 address**  into your browser to test  **Apache**

![Prepare Lamp Server](https://000004.awsstudygroup.com/images/6-AWSFCJmanagement-linux/6.1-Lampserveronec2linux/0009-lampserveronec2linux.png?featherlight=false&width=90pc)

9.  Execute some commands to grant permission

-   Add your user (in this case  **ec2-user**) to the apache group

```
sudo usermod -a -G apache ec2-user

```

-   Change ownership of group  **/var/www**  and its contents to apache group

```
sudo chown -R ec2-user:apache /var/www

```

-   To add group write permissions and set group IDs on subdirectories in the future, change the directory permissions of  **/var/www**  and its subdirectories.

```
sudo chmod 2775 /var/www && find /var/www -type d -exec sudo chmod 2775 {} \;

```

-   To add group write permissions, recursively change the permissions for the file  **/var/www**  and its subdirectories:

```
find /var/www -type f -exec sudo chmod 0664 {} \;

```

![Prepare Lamp Server](https://000004.awsstudygroup.com/images/6-AWSFCJmanagement-linux/6.1-Lampserveronec2linux/00010-lampserveronec2linux.png?featherlight=false&width=90pc)


# TEST LAMP SERVER

#### Check LAMP server

1.  We perform a test of the LAMP server. Create a PHP file.

```
echo "<?php phpinfo(); ?>" > /var/www/html/phpinfo.php

```

![Prepare Lamp Server](https://000004.awsstudygroup.com/images/6-AWSFCJmanagement-linux/6.1-Lampserveronec2linux/00011-lampserveronec2linux.png?featherlight=false&width=90pc)

2.  In the  **EC2**  interface

-   Select  **Instances**
-   Select  **Linux-instance**
-   Copy  **Public IPv4 DNS**

![Prepare Lamp Server](https://000004.awsstudygroup.com/images/6-AWSFCJmanagement-linux/6.1-Lampserveronec2linux/00012-lampserveronec2linux.png?featherlight=false&width=90pc)

3.  Paste the following command into the browser:

```
http://my.public.dns.amazonaws.com/phpinfo.php

```

![Prepare Lamp Server](https://000004.awsstudygroup.com/images/6-AWSFCJmanagement-linux/6.1-Lampserveronec2linux/00013-lampserveronec2linux.png?featherlight=false&width=90pc)

4.  Verify the installed packages again with the following command:

```
sudo yum list installed httpd mariadb-server php-mysqlnd

```

![Prepare Lamp Server](https://000004.awsstudygroup.com/images/6-AWSFCJmanagement-linux/6.1-Lampserveronec2linux/00014-lampserveronec2linux.png?featherlight=false&width=90pc)

5.  Delete the file  **phpinfo.php**

```
rm /var/www/html/phpinfo.php

```

![Prepare Lamp Server](https://000004.awsstudygroup.com/images/6-AWSFCJmanagement-linux/6.1-Lampserveronec2linux/00015-lampserveronec2linux.png?featherlight=false&width=90pc)

# CONFIGURE THE DATABASE SERVER

#### Database server security configuration

The  **mysql_secure_installation**  command will guide you through the process of setting a root password and removing unsafe features from your installation.

1.  Start the MariaDB server.

```
sudo systemctl start mariadb

```

![Prepare Lamp Server](https://000004.awsstudygroup.com/images/6-AWSFCJmanagement-linux/6.1-Lampserveronec2linux/00016-lampserveronec2linux.png?featherlight=false&width=90pc)

2.  Run  **mysql_secure_installation**

```
sudo mysql_secure_installation

```

-   By default, the root account is no password set. Press  **Enter.**
    
-   Enter  **Y**  to set the password and enter the password. Example here using password  **123Admin**
    

You must write down the  **root**  password to use the  **Database**  configuration for  **Nodejs app**

In addition, you should note the following:

Setting a  **root**  password for MariaDB is the most basic measure to secure your database. When you build or install a database-driven application, you typically create a database service user for that application and avoid using the root account for anything but database administration.

-   Enter Y to remove anonymous user accounts.
    
-   Enter Y to disable remote root login.
    
-   Enter Y to remove the test database.
    
-   Type Y to reload privilege tables and save your changes.
    

![Prepare Lamp Server](https://000004.awsstudygroup.com/images/6-AWSFCJmanagement-linux/6.1-Lampserveronec2linux/00017-lampserveronec2linux.png?featherlight=false&width=90pc)

3.  Complete security configuration for the database server

![Prepare Lamp Server](https://000004.awsstudygroup.com/images/6-AWSFCJmanagement-linux/6.1-Lampserveronec2linux/00018-lampserveronec2linux.png?featherlight=false&width=90pc)

4.  If you want the MariaDB server to start every boot, enter the following command:

```
sudo systemctl enable mariadb

```

![Prepare Lamp Server](https://000004.awsstudygroup.com/images/6-AWSFCJmanagement-linux/6.1-Lampserveronec2linux/00019-lampserveronec2linux.png?featherlight=false&width=90pc)

# INSTALL PHPMYADMIN

#### Install phpMyAdmin

**phpMyAdmin**  is a web-based database management tool that you can use to view and edit MySQL databases on your EC2 instances. Follow the steps below to install and configure  **phpMyAdmin**  on your Amazon Linux instance.

1.  Install the required  **dependency**

```
sudo yum install php-mbstring php-xml -y

```

![Prepare Lamp Server](https://000004.awsstudygroup.com/images/6-AWSFCJmanagement-linux/6.1-Lampserveronec2linux/00020-lampserveronec2linux.png?featherlight=false&width=90pc)

2.  Restart  **Apache**

```
sudo systemctl restart httpd

```

![Prepare Lamp Server](https://000004.awsstudygroup.com/images/6-AWSFCJmanagement-linux/6.1-Lampserveronec2linux/00021-lampserveronec2linux.png?featherlight=false&width=90pc)

3.  Restart  **php-fpm**.

```
sudo systemctl restart php-fpm

```

![Prepare Lamp Server](https://000004.awsstudygroup.com/images/6-AWSFCJmanagement-linux/6.1-Lampserveronec2linux/00022-lampserveronec2linux.png?featherlight=false&width=90pc)

4.  Navigate to the Apache document root at  **/var/www/html**.

```
cd /var/www/html

```

![Prepare Lamp Server](https://000004.awsstudygroup.com/images/6-AWSFCJmanagement-linux/6.1-Lampserveronec2linux/00023-lampserveronec2linux.png?featherlight=false&width=90pc)

5.  Download  **phpMyAdmin**

```
wget https://www.phpmyadmin.net/downloads/phpMyAdmin-latest-all-languages.tar.gz

```

![Prepare Lamp Server](https://000004.awsstudygroup.com/images/6-AWSFCJmanagement-linux/6.1-Lampserveronec2linux/00024-lampserveronec2linux.png?featherlight=false&width=90pc)

6.  Create a folder  **phpMyAdmin**  and extract it with the following command.

```
mkdir phpMyAdmin && tar -xvzf phpMyAdmin-latest-all-languages.tar.gz -C phpMyAdmin --strip-components 1

```

![Prepare Lamp Server](https://000004.awsstudygroup.com/images/6-AWSFCJmanagement-linux/6.1-Lampserveronec2linux/00025-lampserveronec2linux.png?featherlight=false&width=90pc)

7.  Remove the  **phpMyAdmin-latest-all-languages.tar.gz tarball**.

```
rm phpMyAdmin-latest-all-languages.tar.gz

```

![Prepare Lamp Server](https://000004.awsstudygroup.com/images/6-AWSFCJmanagement-linux/6.1-Lampserveronec2linux/00026-lampserveronec2linux.png?featherlight=false&width=90pc)

8.  If  **MySQL**  server is not running, start

```
sudo systemctl start mariadb

```

![Prepare Lamp Server](https://000004.awsstudygroup.com/images/6-AWSFCJmanagement-linux/6.1-Lampserveronec2linux/00027-lampserveronec2linux.png?featherlight=false&width=90pc)

9.  In the  **EC2**  interface

-   Select  **Instances**
-   Select  **Linux-instance**
-   Copy  **Public IPv4 DNS**

![Prepare Lamp Server](https://000004.awsstudygroup.com/images/6-AWSFCJmanagement-linux/6.1-Lampserveronec2linux/00028-lampserveronec2linux.png?featherlight=false&width=90pc)

10.  Paste  **Public IPv4 DNS**  into the browser with the following command:

```
http://my.public.dns.amazonaws.com/phpMyAdmin

```

-   You will see the  **phpMyAdmin**  login page.
    
-   Proceed to login with user name:  **root**  and password:  **123Admin**.
    
-   Select  **Login**
    

The root account and password have been configured in the database server security configuration step

![Prepare Lamp Server](https://000004.awsstudygroup.com/images/6-AWSFCJmanagement-linux/6.1-Lampserveronec2linux/00029-lampserveronec2linux.png?featherlight=false&width=90pc)

11.  In the  **phpMyAdmin**  interface

-   Create a new database by selecting  **New**

![Prepare Lamp Server](https://000004.awsstudygroup.com/images/6-AWSFCJmanagement-linux/6.1-Lampserveronec2linux/00030-lampserveronec2linux.png?featherlight=false&width=90pc)

12.  Database Configuration

-   Enter database name as  **awsuser**
-   Then select  **Create**

![Prepare Lamp Server](https://000004.awsstudygroup.com/images/6-AWSFCJmanagement-linux/6.1-Lampserveronec2linux/00031-lampserveronec2linux.png?featherlight=false&width=90pc)

13.  Finish creating a database

![Prepare Lamp Server](https://000004.awsstudygroup.com/images/6-AWSFCJmanagement-linux/6.1-Lampserveronec2linux/00032-lampserveronec2linux.png?featherlight=false&width=90pc)

14.  Perform the  **SQL Schema**  step to create a  **user**  table to manage user information for the database. Execute the following  **SQL**  query:

```
CREATE TABLE `awsuser`.`user` ( `id` INT NOT NULL AUTO_INCREMENT , `first_name` VARCHAR(45) NOT NULL , `last_name` VARCHAR(45) NOT NULL , `email` VARCHAR(45) NOT NULL , `phone` VARCHAR(45) NOT NULL , `comments` TEXT NOT NULL , `status` VARCHAR(10) NOT NULL DEFAULT 'active' , PRIMARY KEY (`id`)) ENGINE = InnoDB;

```

-   Select  **awsuser**  database just created
-   Select  **SQL**
-   Paste the code  **SQL**  query into
-   Select  **Format**  to customize the format of SQL
-   Then select  **Go**

![Prepare Lamp Server](https://000004.awsstudygroup.com/images/6-AWSFCJmanagement-linux/6.1-Lampserveronec2linux/00033-lampserveronec2linux.png?featherlight=false&width=90pc)

15.  Complete database creation and create tables in the database.

Information about the database must be correct and stored to perform the configuration for the application

![Prepare Lamp Server](https://000004.awsstudygroup.com/images/6-AWSFCJmanagement-linux/6.1-Lampserveronec2linux/00034-lampserveronec2linux.png?featherlight=false&width=90pc)
