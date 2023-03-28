## How To Deploy MEAN Stack To Ubuntu In AWS

Implement a simple Book Register web form using MEAN stack.

## PREREQUISITES ##

**Create a new EC2 Instance of t2.nano family with Ubuntu Server 22.04 LTS (HVM) image**

**Connect to the instance through an SSH client/web**


## Step 1

Download updates for ubuntu

`sudo apt update`

![Download updates for ubuntu](./images/sudo%20apt%20update.jpg)

Upgrade ubuntu

`sudo apt upgrade`

![Upgrade ubuntu](./images/sudo%20apt%20upgrade.jpg)

Add certificates

`sudo apt -y install curl dirmngr apt-transport-https lsb-release ca-certificates`

`curl -sL https://deb.nodesource.com/setup_18.x | sudo -E bash -`

![Add certificates](./images/add%20certificate.jpg)

![Add certificates](./images/add%20repo.jpg)

## Install NodeJS ##


Install NodeJS and NVM

`sudo apt install -y nodejs`

![Install NodeJS](./images/install%20nodejs%20and%20nvm.jpg)


## Step 2

Install MongoDB

MongoDB stores data in flexible, JSON-like documents. Fields in a database can vary from document to document and data structure can be changed over time.

`sudo apt update`

![Install MongoDB](./images/Import%20Mongodb%20GPG%20key.jpg)

![Install MongoDB](./images/Add%20the%20MongoDB%20repository%20to%20your%20system%E2%80%99s%20package%20manager.jpg)

Start The server and verify that the service is up

`sudo systemctl mongod start`
`sudo systemctl mongod status`

![Start The server](./images/start%20and%20check%20mongodb's%20status.jpg)

Install npm – Node package manager and verify.

`sudo apt install -y npm`
`npm -v`

![Start The server](./images/npm%20installed.jpg)

Install body-parser package

`sudo npm install body-parser`

![Install body-parser package](./images/Install%20body-parser%20package.jpg)

Create a folder named ‘Books’

`mkdir Books && cd Books`

![Create a folder named ‘Books’](./images/Create%20a%20folder%20named%20%E2%80%98Books%E2%80%99.jpg)

In the Books directory, Initialize npm project

`npm init`

![Initialize npm project](./images/Initialize%20npm%20project.jpg)

Add a file to it named server.js

`vi server.js`

![Add a file to it named server.js](./images/create%20a%20file%20server.js.jpg)


Copy and paste the web server code below into the server.js file.

![Add a file to it named server.js](./images/code%20for%20sever%2Cjs.jpg)

 ## INSTALL EXPRESS AND SET UP ROUTES TO THE SERVER ##

 ## Step 3 ##

 Express is a minimal and flexible Node.js web application framework that provides features for web and mobile applications. We will use Express in to pass book information to and from our MongoDB database.

 `sudo npm install express mongoose`

 ![Install Express Mongoose](./images/install%20moongose.jpg)

 In ‘Books’ folder, create a folder named apps

 `mkdir apps && cd apps`

  ![create apps directory](./images/create%20a%20folder%20named%20apps.jpg)

 Create a file named routes.js

 `vi routes.js`

 ![create routes.js](./images/create%20routes.jpg)

 Copy and paste the code below into routes.js

 ![code routes.js](./images/code%20in%20routes.jpg)

 In the ‘apps’ folder, create a folder named models

 `mkdir models && cd models`

![create models](./images/create%20a%20folder%20named%20models.jpg)

Create a file named book.js

`vi book.js`

![create file book.js](./images/create%20book.js.jpg)

Copy and paste the code below into ‘book.js’

![create](./images/code%20in%20books.js.jpg)

## Step 4 – Access the routes with AngularJS ##

AngularJS provides a web framework for creating dynamic views in your web applications. In this tutorial, we use AngularJS to connect our web page with Express and perform actions on our book register.

Change the directory back to ‘Books’

`cd ../..`

![change to books](./images/change%20back%20to%20Books%20directory.jpg)

Create a folder named public

`mkdir public && cd public`

![create folder public](./images/Create%20a%20folder%20named%20public.jpg)

Add a file named script.js

`vi script.js`

![create script.js](./images/code%20in%20script.js.jpg)

Copy and paste the Code below (controller configuration defined) into the script.js file.

![code for script.js](./images/code%20in%20script.js.jpg)

In public folder, create a file named index.html;

`vi index.html`

![create index.html](./images/index.html.jpg)

Copy and paste the code below into index.html file.

![code for index.html](./images/code%20in%20index.html.jpg)

Change the directory back up to Books

`cd ..`

![change to Books](./images/Change%20the%20directory%20back%20up%20to%20Books.jpg)


Start the server by running this command:

`node server.js`


![node server.js](./images/node%20server.js.jpg)

Find the public ip address

`curl -s http://169.254.169.254/latest/meta-data/public-ipv4`

![public ip](./images/public%20ip.jpg)

Browser output

![public ip](./images/result.jpg)