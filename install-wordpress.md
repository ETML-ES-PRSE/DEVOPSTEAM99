# Install WordPress

## Prerequisites

* Apache is setup
* MySql client is setup

## Prepare Apache for Wordpress hosting

* [Digital Ocean - Virtual Host](https://www.digitalocean.com/community/tutorials/how-to-install-lamp-stack-on-ubuntu#step-4-creating-a-virtual-host-for-your-website)

* Create a folder for our wordpress instance

```
sudo mkdir /var/www/devopsteam99
sudo chown -R $USER:$USER /var/www/devopsteam99
sudo chmod -R 755 /var/www/devopsteam99/
```

* Create and custom vhost config

```
sudo cp /etc/apache2/sites-available/000-default.conf /etc/apache2/sites-available/devopsteam99.cld.education.conf
```

```
<VirtualHost *:8000>
        ServerName devopsteam99
        ServerAlias devopsteam99.cld.education
        ServerAdmin webmaster@localhost
        DocumentRoot /var/www/devopsteam99.cld.education
        ErrorLog ${APACHE_LOG_DIR}/devopsteam99-error.log
        CustomLog ${APACHE_LOG_DIR}/devopsteam99-access.log combined
</VirtualHost>
``

* Enable vhost

```
sudo a2ensite devopsteam99.cld.education.conf
`` 

* Disable default site

```
sudo a2dissite 000-default-conf
```

* Reload apache2 service

```
sudo systemctl reload apache2
```

* Set ServerName as global apache variable

```
sudo vi /etc/apache2/apache2.conf
```

```
add "ServerName devopsteam99.cld.education" at the end the file
```

* Check the apache configuration

```
sudo apache2ctl configtest
Syntax OK
```

## Adjust Apache for Wordpress

* [Digital Ocean - htaccess](https://www.digitalocean.com/community/tutorials/how-to-install-wordpress-on-ubuntu-22-04-with-a-lamp-stack#step-3-adjusting-apache-s-configuration-to-allow-for-htaccess-overrides-and-rewrites)

* Enable rewrite module on Apache

```
// /etc/apache2/sites-available/devopsteam99.cld.education.conf
  <VirtualHost *:80>
. . .
    <Directory /var/www/devopsteam99/>
        AllowOverride All
    </Directory>
. . .
</VirtualHost>
```

```
sudo a2enmod rewrite
Enabling module rewrite.
To activate the new configuration, you need to run:
  systemctl restart apache2
```

## Download Wodress App

* [Digital Ocean - Download Wordpress](https://www.digitalocean.com/community/tutorials/how-to-install-wordpress-on-ubuntu-22-04-with-a-lamp-stack#step-4-downloading-wordpress)

* Download the latest version of Wordpress in a tmp folder and uncompressed the archive

```
cd /tmp
curl -O https://wordpress.org/latest.tar.gz
tar xzvf latest.tar.gz
```

## Adjusting the permissions

* [Digital Ocean - Adjusting permissions](https://www.digitalocean.com/community/tutorials/how-to-install-wordpress-on-ubuntu-22-04-with-a-lamp-stack#step-5-configuring-the-wordpress-directory)

* Add your user in the www-data group

```
sudo usermod -a -G www-data $(whoami)
sudo chgrp www-data /var/www/html -R
```
