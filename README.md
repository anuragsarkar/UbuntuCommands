
# Linux Ubuntu Commands for Installing PHP, MySQL, GIT, VSCode, Node & Angular [2019].

# Installing Git for Ubuntu

$ sudo apt update

$ sudo apt install git

$ git --version

# Command for adding permissions for folder & files

$ sudo chmod -R o+rw /var/www

# Command for Installing Apache Server

$ sudo apt-get install apache2

# Installing PHP 5.6 & 7.2 for Ubuntu 

$ sudo apt-get install python-software-properties
$ sudo add-apt-repository ppa:ondrej/php
$ sudo apt-get update
$ sudo apt-get install -y php5.6

# Install PHP

$ sudo apt-get install php libapache2-mod-php

# Install PHP 7.2

$ sudo apt-get install python-software-properties
$ sudo add-apt-repository ppa:ondrej/php
$ sudo apt-get update
$ sudo apt-get install -y php7.2

**Check using php -v command

**Create a file with name of info and save it. Then open it using localhost/info.php. You can check php version there**

$ sudo nano /var/www/html/info.php

**Restart apache server**

$ sudo systemctl restart apache2

# Install MySQL Server on Ubuntu 

$ sudo apt-get install mysql-server

**Check MySql on Terminal**

$ sudo mysql -u root -p


# Install PHP Strom any version download the tar.gz file or download using command link.
$ wget https://download-cf.jetbrains.com/webide/PhpStorm-2016.1.2.tar.gz

**Goto Download folder and run to extract it**

$ tar xvf PhpStorm-2016.1.2.tar.gz

**Move extracted folder opt directory**

$ sudo mv PhpStorm-145.1616.3/ /opt/phpstorm/

**Create symlink**

$ sudo ln -s /opt/phpstorm/bin/phpstorm.sh /usr/local/bin/phpstorm

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

# Change Permission in Ubuntu

**run the command sudo chmod -R a+rwx "/path/to/folder" 

# Fix Warning in ./libraries/sql.lib.php#601 Error for phpmyadmin in ubunu 18.04 and PHP 7.2

**Warning in ./libraries/sql.lib.php#601
**count(): Parameter must be an array or an object that implements Countable
**Backtrace

# Solution

**Go to sudo nano /usr/share/phpmyadmin/libraries/sql.lib.php file

**And replace function PMA_isRememberSortingOrder() code with below code

**Refer to [this link](https://stackoverflow.com/questions/48001569/phpmyadmin-count-parameter-must-be-an-array-or-an-object-that-implements-co)

`function PMA_isRememberSortingOrder($analyzed_sql_results)
{
    return $GLOBALS['cfg']['RememberSorting']
        && ! ($analyzed_sql_results['is_count']
            || $analyzed_sql_results['is_export']
            || $analyzed_sql_results['is_func']
            || $analyzed_sql_results['is_analyse'])
        && $analyzed_sql_results['select_from']
        && ((empty($analyzed_sql_results['select_expr']))
            || (count($analyzed_sql_results['select_expr']) == 1)
            && ($analyzed_sql_results['select_expr'][0] == '*'))
               && count($analyzed_sql_results['select_tables']) == 1;
}`
