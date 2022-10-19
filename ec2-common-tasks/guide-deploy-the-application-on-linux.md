
# DEPLOY THE APPLICATION ON LINUX

#### Deploy applications on Linux

1.  We use git to clone the source code. First of all, install git with the following command:

```
sudo yum install git

```

![AWS User Management ](https://000004.awsstudygroup.com/images/6-AWSFCJmanagement-linux/6.3-awsfcjmanagement/0001-awsfcjmanagement.png?featherlight=false&width=90pc)

2.  Check successful git installation with command

```
git version

```

![AWS User Management ](https://000004.awsstudygroup.com/images/6-AWSFCJmanagement-linux/6.3-awsfcjmanagement/0002-awsfcjmanagement.png?featherlight=false&width=90pc)

3.  Clone  **repository**  application code

```
cd ~ec2-user
git clone https://github.com/First-Cloud-Journey/000004-EC2.git

```

![AWS User Management ](https://000004.awsstudygroup.com/images/6-AWSFCJmanagement-linux/6.3-awsfcjmanagement/0003-awsfcjmanagement.png?featherlight=false&width=90pc)

4.  Go to the lab directory  **000004-EC2**  and check the files

```
cd 000004-EC2

```

```
ls

```

![AWS User Management ](https://000004.awsstudygroup.com/images/6-AWSFCJmanagement-linux/6.3-awsfcjmanagement/0004-awsfcjmanagement.png?featherlight=false&width=90pc)

5.  **NPM**  stands for  **Node package manager**  and is a tool to create and manage Javascript programming libraries for Node.js. Using  **npm init**  to initialize the project will generate a sample package.json file.

```
npm init

```

You proceed to configure the application’s information which is saved in the file  **package.json**

![AWS User Management ](https://000004.awsstudygroup.com/images/6-AWSFCJmanagement-linux/6.3-awsfcjmanagement/0005-awsfcjmanagement.png?featherlight=false&width=90pc)

6.  Next, we do  **dependencies installation**

-   express
-   Dotenv
-   express-handlebars
-   body-parser
-   mysql

```
npm install express dotenv express-handlebars body-parser mysql

```

![AWS User Management ](https://000004.awsstudygroup.com/images/6-AWSFCJmanagement-linux/6.3-awsfcjmanagement/0006-awsfcjmanagement.png?featherlight=false&width=90pc)

7.  Check the installed dependencies. The  **node_modules**  folder appears.

```
ls

```

![AWS User Management ](https://000004.awsstudygroup.com/images/6-AWSFCJmanagement-linux/6.3-awsfcjmanagement/0007-awsfcjmanagement.png?featherlight=false&width=90pc)

8.  Create file  **.env**

```
touch .env

```

![AWS User Management ](https://000004.awsstudygroup.com/images/6-AWSFCJmanagement-linux/6.3-awsfcjmanagement/0008-awsfcjmanagement.png?featherlight=false&width=90pc)

9.  Use  **vi**  to edit the  **.env**  file. We perform the database configuration:

```
DB_HOST = 'localhost'
DB_NAME = 'DB_NAME'
DB_USER = 'root'
DB_PASS = 'password'

```

In the lab, we use the database name  **awsuser**  and the database information has been configured in the database security configuration step (password:  **123Admin**)

![AWS User Management ](https://000004.awsstudygroup.com/images/6-AWSFCJmanagement-linux/6.3-awsfcjmanagement/0009-awsfcjmanagement.png?featherlight=false&width=90pc)

10.  Check database configuration

```
ls -a

```

![AWS User Management ](https://000004.awsstudygroup.com/images/6-AWSFCJmanagement-linux/6.3-awsfcjmanagement/00010-awsfcjmanagement.png?featherlight=false&width=90pc)

11.  Restart  **Express server**. Use  **Nodemon**  to save time

```
npm install --save-dev nodemon

```

![AWS User Management ](https://000004.awsstudygroup.com/images/6-AWSFCJmanagement-linux/6.3-awsfcjmanagement/00011-awsfcjmanagement.png?featherlight=false&width=90pc)

12.  Starting  **local server**

```
npm start

```

![AWS User Management ](https://000004.awsstudygroup.com/images/6-AWSFCJmanagement-linux/6.3-awsfcjmanagement/00012-awsfcjmanagement.png?featherlight=false&width=90pc)

13.  In the  **EC2**  interface

-   Select  **Instances**
-   Select  **Linux-instance**
-   Copy  **Public IPv4 address**

![AWS User Management ](https://000004.awsstudygroup.com/images/6-AWSFCJmanagement-linux/6.3-awsfcjmanagement/00013-awsfcjmanagement.png?featherlight=false&width=90pc)

14.  Paste  **Public IPv4 address**  into the browser and port  **5000**. Observe the  **AWS FCJ Management**  interface

![AWS User Management ](https://000004.awsstudygroup.com/images/6-AWSFCJmanagement-linux/6.3-awsfcjmanagement/00014-awsfcjmanagement.png?featherlight=false&width=90pc)

15.  In the  **phpMyAdmin**  interface, we execute  **SQL Dummy Data**

-   Select  **awsuser**  database
-   Select  **SQL**
-   Paste the SQL query code in

```
INSERT INTO `user` 
(`id`, `first_name`,  `last_name`,    `email`,                 `phone`,         `comments`, `status`) VALUES
(NULL, 'Amanda',      'Nunes',        'anunes@ufc.com',        '012345 678910', '',          'active'),
(NULL, 'Alexander',   'Volkanovski',  'avolkanovski@ufc.com',  '012345 678910', '',          'active'),
(NULL, 'Khabib',      'Nurmagomedov', 'knurmagomedov@ufc.com', '012345 678910', '',          'active'),
(NULL, 'Kamaru',      'Usman',        'kusman@ufc.com',        '012345 678910', '',          'active'),
(NULL, 'Israel',      'Adesanya',     'iadesanya@ufc.com',     '012345 678910', '',          'active'),
(NULL, 'Henry',       'Cejudo',       'hcejudo@ufc.com',       '012345 678910', '',          'active'),
(NULL, 'Valentina',   'Shevchenko',   'vshevchenko@ufc.com',   '012345 678910', '',          'active'),
(NULL, 'Tyron',       'Woodley',      'twoodley@ufc.com',      '012345 678910', '',          'active'),
(NULL, 'Rose',        'Namajunas ',   'rnamajunas@ufc.com',    '012345 678910', '',          'active'),
(NULL, 'Tony',        'Ferguson ',    'tferguson@ufc.com',     '012345 678910', '',          'active'),
(NULL, 'Jorge',       'Masvidal ',    'jmasvidal@ufc.com',     '012345 678910', '',          'active'),
(NULL, 'Nate',        'Diaz ',        'ndiaz@ufc.com',         '012345 678910', '',          'active'),
(NULL, 'Conor',       'McGregor ',    'cmcGregor@ufc.com',     '012345 678910', '',          'active'),
(NULL, 'Cris',        'Cyborg ',      'ccyborg@ufc.com',       '012345 678910', '',          'active'),
(NULL, 'Tecia',       'Torres ',      'ttorres@ufc.com',       '012345 678910', '',          'active'),
(NULL, 'Ronda',       'Rousey ',      'rrousey@ufc.com',       '012345 678910', '',          'active'),
(NULL, 'Holly',       'Holm ',        'hholm@ufc.com',         '012345 678910', '',          'active'),
(NULL, 'Joanna',      'Jedrzejczyk ', 'jjedrzejczyk@ufc.com',  '012345 678910', '',          'active')

```

-   Select  **Format**
-   Select  **Go**

![AWS User Management ](https://000004.awsstudygroup.com/images/6-AWSFCJmanagement-linux/6.3-awsfcjmanagement/00015-awsfcjmanagement.png?featherlight=false&width=90pc)

16.  Refresh the application interface

![AWS User Management ](https://000004.awsstudygroup.com/images/6-AWSFCJmanagement-linux/6.3-awsfcjmanagement/00016-awsfcjmanagement.png?featherlight=false&width=90pc)

17.  View user

![AWS User Management ](https://000004.awsstudygroup.com/images/6-AWSFCJmanagement-linux/6.3-awsfcjmanagement/00017-awsfcjmanagement.png?featherlight=false&width=90pc)

18.  Edit users

![AWS User Management ](https://000004.awsstudygroup.com/images/6-AWSFCJmanagement-linux/6.3-awsfcjmanagement/00018-awsfcjmanagement.png?featherlight=false&width=90pc)

19.  Add users

![AWS User Management ](https://000004.awsstudygroup.com/images/6-AWSFCJmanagement-linux/6.3-awsfcjmanagement/00019-awsfcjmanagement.png?featherlight=false&width=90pc)

20.  Search for users

![AWS User Management ](https://000004.awsstudygroup.com/images/6-AWSFCJmanagement-linux/6.3-awsfcjmanagement/00020-awsfcjmanagement.png?featherlight=false&width=90pc)

21.  Database after inserting the item

![AWS User Management ](https://000004.awsstudygroup.com/images/6-AWSFCJmanagement-linux/6.3-awsfcjmanagement/00021-awsfcjmanagement.png?featherlight=false&width=90pc)

22.  Interface of the instance when starting the local server

![AWS User Management ](https://000004.awsstudygroup.com/images/6-AWSFCJmanagement-linux/6.3-awsfcjmanagement/00022-awsfcjmanagement.png?featherlight=false&width=90pc)
