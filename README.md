
# Linux Ubuntu Commands for Installing PHP, MySQL, GIT, VSCode, Node & Angular [2019].

# Installing Git for Ubuntu

$ sudo apt update

$ sudo apt install git

$ git --version

# Command for adding permissions for folder & files

$ sudo chmod -R o+rw /var/www

# Command for installing apache

$ sudo apt-get install apache2

# Installing PHP for Ubuntu 18.04

$ sudo apt-get install php libapache2-mod-php

**Note**:Create a file with name of info and save it. Then open it using localhost/info.php. You can check php version there

$ sudo nano /var/www/html/info.php

# Restart apache server
$ sudo systemctl restart apache2

# Install MySQL Server on Ubuntu 
$ sudo apt-get install mysql-server

# Check MySql on Terminal
$ sudo mysql -u root -p

# Installing Node JS for Angular JS

**We need to have CURL & python software package in our system for installing Node.**
    
$ sudo apt-get install curl

$ sudo apt-get install python-software-properties
 
    
# Add Node JS PPA & Install it.
    
$ curl -sL https://deb.nodesource.com/setup_9.x | sudo -E bash -

$ sudo apt-get install nodejs

$ node -v

$ npm -v

# Installing Angular CLI for creating Angular 2 App.</h2>

$ npm install -g angular-cli

$ ng new myfirstangproject

$ cd mynewfirstangproject 

$ ng serve         

**After this you need to go to your browser and open http://localhost:4200/.**