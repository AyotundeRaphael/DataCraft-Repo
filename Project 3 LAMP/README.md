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

<?php
phpinfo();
 