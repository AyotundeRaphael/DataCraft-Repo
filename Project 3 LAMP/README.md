# LAMP STACK Implementation #
## Before performing the implementation below I already done the followings: ##

Registered an account with AWS Cloud Provider

Created a Free EC2 Instance (with Ubuntu Linux OS option)

I have downloaded keypair.pem 

setup security group that use to connect server remotely through ssh (port 22)

## connect remotely to the Ec2 instance using Git Bash terminal ##

![Alt text](Images/picture1.png)

## update the server using `sudo apt update command` ##

![Alt text](Images/picture2.png)

## installing Apache Server using `sudo apt install apache2` ##

Apache was installed on the EC2 instance. behold pictures below.

![Alt text](Images/picture3.png)

![Alt text](Images/picture4.png)

## Verifying that Apache2 is running using the `sudo systemctl status apache2` command ##

![Alt text](Images/picture5.png)

## An attempt to run apache server locally in the ubuntu shell using `curl http://localhost:80` or curl `http://127.0.0.1:80`command

![Alt text](Images/picture6.png)

## copying the ec2 public ipaddress and pasting it on the browser address bar displays the image below: ##

![Alt text](Images/picture7.png)

## Installing Mysql-server on the EC2 machine using the command `sudo apt install myql-server `##

mysql-server is now installed for database services.

![Alt text](Images/picture8.png)

## logged into Mysql using `sudo mysql` command ##

![Alt text](Images/picture9.png)

![Alt text](Images/picture10.png)


## Installing Php: ##
Using `sudo apt install php`

![Alt text](Images/picture11.png)

## configuring php to handle php files ##
using `sudo apt install libapache2-mod-php` command

![Alt text](Images/picture12.png)

## establishing communication between php and mysql ##
using `sudo apt install php-mysql` command

![Alt text](Images/picture13.png)

## trying to create a Virtual Host for the Website using Apache ## 
creating a directory called `projectlamp` by using the `mkdir` command in 
`sudo mkdir /var/www/projectlamp` and changing the ownership by assigning ownership to `$USER`by using this command
`sudo chown -R $USER:$USER /var/www/projectlamp`
then open the configuration file in Apache named `sites-available` with this command `sudo vi /etc/apache2/sites-available/projectlamp.conf`

![Alt text](Images/Picture14.png)

then inside the blank file that opens copy this code 
`<VirtualHost *:80>
    ServerName projectlamp
    ServerAlias www.projectlamp 
    ServerAdmin webmaster@localhost
    DocumentRoot /var/www/projectlamp
    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>`

![Alt text](Images/Picture15.png)

## To display the php page we need to:
disable 000-default and enable projectlamp by the following commands: ##
  `sudo a2dissite 000-default`
  `sudo a2ensite projectlamp`
  `sudo apache2ctl configtest`
  `sudo systemctl reload apache2`

![Alt text](Images/Picture16.png) 

## To enable the PHP on the website we do the following:##
* give `index.php` the priority over `index.html`
using the following commands/codes.
`sudo vim /etc/apache2/mods-enabled/dir.conf`
`<IfModule mod_dir.c>
        #Change this:
        #DirectoryIndex index.html index.cgi index.pl index.php index.xhtml index.htm
        #To this:
        `DirectoryIndex index.php index.html index.cgi index.pl index.xhtml index.htm`
</IfModule>`

then create index.php in the projectlamp using:  
`sudo vim /var/www/projectlamp/index.php`

then insert this code into index.php file

` <?php
phpinfo();`

refresh on the broswer address bar with the public IP of the instance to display the php page below

![Alt text](Images/Picture17.png)

To disable this page use `rm`command in 
`sudo rm /var/www/projectlamp/index.php`

then refresh again to have. 

![Alt text](Images/Picture18.png)

thank you 


















 