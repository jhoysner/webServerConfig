Configure apache server ubuntu 14.04


1) Install programs

apt-get update
apt-get upgrade
apt-get install apache2
apt-get install php5
apt-get install mysql
apt-get install phpmyadmin

Change this value
/etc/phpmyadmin/config.inc.php
$cfg['ExecTimeLimit'] = xtime;


- Enable mod rewrite from terminal

Execute from terminal
root# a2enmod rewrite

add this into /etc/apache2/sites-enabled/000-default.conf
root# nano /etc/apache2/sites-enabled/000-default.conf

<Directory /var/www/html>
        Options Indexes FollowSymLinks MultiViews
        AllowOverride All
        Order allow,deny
        allow from all
</Directory>
