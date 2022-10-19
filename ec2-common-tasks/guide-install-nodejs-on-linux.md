# NODEJS APPLICATION ON EC2 LINUX

#### Deploy an AWS User Management Application on Amazon Linux 2

-   AWS User Management is built with Node.js, Express, Express-Handlebars, and MySQL
-   We will install LAMP web server on Amazon Linux 2 to use MySQL database (MariaDB).
-   Create database, table, insert item on  **phpMyAdmin**  interface
-   Also install  **Nodejs Runtime Environment**
-   Deploy the application and experience the application’s view, add, delete, edit, search features.(CRUD)

## INSTALL NODEJS ON LINUX

#### Install Nodejs on Amazon Linux 2

In the lab, we use Node.js with the SDK for JavaScript to set up and run the Node.js web application on Amazon Elastic Compute Cloud (Amazon EC2).

You must configure  **Security Group**  to allow  **SSH(port 22)**,  **HTTP(port 80)**,  **HTTPS(port 443)**  and  **app using Nodejs(port 5000)**

1.  Install  **node version manager (nvm)**  ) by typing the following in the following command line:

```
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.34.0/install.sh | bash

```

We will be using nvm to install Node.js because nvm can install multiple versions of Node.js and allows you to switch between them.

![Set up Nodejs on EC2 Linux](https://000004.awsstudygroup.com/images/6-AWSFCJmanagement-linux/6.2-SetupNodejsonec2linux/0001-setupnodejsec2linux.png?featherlight=false&width=90pc)

2.  Enable nvm by typing the following in the command line:

```
. ~/.nvm/nvm.sh

```

![Set up Nodejs on EC2 Linux](https://000004.awsstudygroup.com/images/6-AWSFCJmanagement-linux/6.2-SetupNodejsonec2linux/0002-setupnodejsec2linux.png?featherlight=false&width=90pc)

3.  Use nvm to install the latest version of Node.js by typing the following in the command line.

```
nvm install 16

```

![Set up Nodejs on EC2 Linux](https://000004.awsstudygroup.com/images/6-AWSFCJmanagement-linux/6.2-SetupNodejsonec2linux/0003-setupnodejsec2linux.png?featherlight=false&width=90pc)

4.  Check installed nodejs successfully

```
node -v

```

```
npm -v

```

![Set up Nodejs on EC2 Linux](https://000004.awsstudygroup.com/images/6-AWSFCJmanagement-linux/6.2-SetupNodejsonec2linux/0004-setupnodejsec2linux.png?featherlight=false&width=90pc)
