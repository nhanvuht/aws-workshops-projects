# NODEJS APPLICATION ON EC2 WINDOWS

#### Deploy application on  **Microsoft Windows Server 2022**  instance

-   AWS User Management is built with  **Node.js, Express, Express-Handlebars, and MySQL**
-   We will install  **XAMPP**  on  **Microsoft Windows Server 2022 Base**  to use  **MySQL(MariaDB)**  database.
-   Create database, table, insert item on  **phpMyAdmin**  interface
-   Also install  **Nodejs Runtime Environment**
-   Deploy the application and experience the application’s view, add, delete, edit, and search features. (CRUD)

## DEPLOY APPLICATION ON WINDOWS INSTANCE

#### Deploy application on Microsoft Windows Server 2022 instance

1.  NPM stands for Node package manager and is a tool to create and manage Javascript programming libraries for Node.js. Using npm init to initialize the project will generate a sample package.json file.

```
npm init

```

![AWS User Management ](https://000004.awsstudygroup.com/images/7-AWSFCJmanagement-windows/7.3-awsfcjmanagement/0001-awsfcjmanagement.png?featherlight=false&width=90pc)

2.  Complete the application’s information configuration

![AWS User Management ](https://000004.awsstudygroup.com/images/7-AWSFCJmanagement-windows/7.3-awsfcjmanagement/0002-awsfcjmanagement.png?featherlight=false&width=90pc)

3.  Next, we do the dependencies installation

```
npm install express dotenv express-handlebars body-parser mysql

```

-   express
-   Dotenv
-   express-handlebars
-   body-parser
-   mysql

![AWS User Management ](https://000004.awsstudygroup.com/images/7-AWSFCJmanagement-windows/7.3-awsfcjmanagement/0003-awsfcjmanagement.png?featherlight=false&width=90pc)

4.  Use  **Visual Studio Code**  to open the source code and create a  **.env**  file used to configure the database

```
DB_HOST = 'localhost'
DB_NAME = 'DB_NAME'
DB_USER = 'root'
DB_PASS = 'password'

```

Since it is a practical lab, we use the root user with a blank password. When you build or install a database-driven application, you generally create a database service user for that application and avoid using the root account for anything but database administration.

![AWS User Management ](https://000004.awsstudygroup.com/images/7-AWSFCJmanagement-windows/7.3-awsfcjmanagement/0004-awsfcjmanagement.png?featherlight=false&width=90pc)

5.  Restart the Express server. Use Nodemon to save time.

```
npm install --save-dev nodemon

```

![AWS User Management ](https://000004.awsstudygroup.com/images/7-AWSFCJmanagement-windows/7.3-awsfcjmanagement/0005-awsfcjmanagement.png?featherlight=false&width=90pc)

6.  Start the local server

```
npm start

```

![AWS User Management ](https://000004.awsstudygroup.com/images/7-AWSFCJmanagement-windows/7.3-awsfcjmanagement/0006-awsfcjmanagement.png?featherlight=false&width=90pc)

7.  Open a browser and go to  localhost:5000

![AWS User Management ](https://000004.awsstudygroup.com/images/7-AWSFCJmanagement-windows/7.3-awsfcjmanagement/0007-awsfcjmanagement.png?featherlight=false&width=90pc)

8.  View user information

![AWS User Management ](https://000004.awsstudygroup.com/images/7-AWSFCJmanagement-windows/7.3-awsfcjmanagement/0008-awsfcjmanagement.png?featherlight=false&width=90pc)

9.  Edit user information

![AWS User Management ](https://000004.awsstudygroup.com/images/7-AWSFCJmanagement-windows/7.3-awsfcjmanagement/0009-awsfcjmanagement.png?featherlight=false&width=90pc)

10.  Add users

![AWS User Management ](https://000004.awsstudygroup.com/images/7-AWSFCJmanagement-windows/7.3-awsfcjmanagement/00010-awsfcjmanagement.png?featherlight=false&width=90pc)

11.  Search for users

![AWS User Management ](https://000004.awsstudygroup.com/images/7-AWSFCJmanagement-windows/7.3-awsfcjmanagement/00011-awsfcjmanagement.png?featherlight=false&width=90pc)
