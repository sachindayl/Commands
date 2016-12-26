#LAMP Installation in ARCH LINUX

This document helps users to easily install LAMP Stack on Arch Linux.

##Apache Installation

First update packages:
```
sudo pacman -Syu
```
Install Apache:
```
sudo pacman -S apache
```
Make it start up at boot:
```
sudo systemctl enable httpd
```
Make apache start now:
```
sudo systemctl start httpd
```
Check status to see if it is running:
```
sudo systemctl status httpd
```
##MySQL Installation

MariaDB is an opensource MySQL database management system. It is a community driven fork of the MySQL project that was developed after Oracle bought MySQL.

To install MySQL:
```
sudo pacman -Syu mariadb mariadb-clients libmariadbclient
```
Install MariaDB data directory:
```
sudo mysql_install_db --user=mysql --basedir=/usr --datadir=/var/lib/mysql
```
Start MySQL and make sure it runs on every boot
```
sudo systemctl start mysqld.service
sudo systemctl enable mysqld.service
```
If there aren't any errors returned, run the program that helps to secure the database:
```
mysql_secure_installation
```
##PHP Installation
To install PHP do:
```
sudo pacman -S php-apache
```
Then go to Arch Wiki and follow the [PHP](https://wiki.archlinux.org/index.php/Apache_HTTP_Server) and follow until testing php page.

##Credits
* [Linode](https://www.linode.com/docs/websites/lamp/lamp-server-on-arch-linux)
* [Ubiquity Hosting](https://www.ubiquityhosting.com/blog/lamp-archlinux-tutorial/)
* [Arch Wiki](https://wiki.archlinux.org/index.php/Apache_HTTP_Server)
