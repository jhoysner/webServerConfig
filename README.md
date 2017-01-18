#Configure apache server ubuntu 14.04

1) Install programs

    apt-get update
    apt-get upgrade
    apt-get install apache2
    apt-get install php5
    apt-get install mysql
    apt-get install phpmyadmin

2) Change this value

        nano /etc/phpmyadmin/config.inc.php 
        $cfg['ExecTimeLimit'] = xtime;

3) Enable mod rewrite from terminal

        a2enmod rewrite

4) add this
    
        nano /etc/apache2/sites-enabled/000-default.conf

    <Directory /var/www/html>
            Options Indexes FollowSymLinks MultiViews
            AllowOverride All
            Order allow,deny
            allow from all
    </Directory>

5) Restart apache server

    service apache2 restart

6) Include phpmyadmin in apache forlder

    Include /etc/phpmyadmin/apache.conf
