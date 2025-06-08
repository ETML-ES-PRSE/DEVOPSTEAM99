# Install WordPress

## Prerequisites

* Apache is setup
* MySql client is setup

## Prepare VHost for Wordpress

* Create wordpress folder

```
sudo mkdir /var/www/wordpress
sudo chown -R $USER:$USER /var/www/wordpress
sudo chmod -R 755 /var/www/wordpress/
```

* Create and custom vhost config

```
sudo cp /etc/apache2/sites-available/000-default.conf /etc/apache2/sites-available/wordpress.conf
```

```
<VirtualHost *:80>
  ...
    ServerAdmin webmaster@localhost
    DocumentRoot /var/www/html/wordpress
   ...
    ErrorLog ${APACHE_LOG_DIR}/wordpress-error.log
    CustomLog ${APACHE_LOG_DIR}/wordpress-access.log combined
</VirtualHost>
``

* Enable vhost

```
sudo a2ensite wordpress.conf
`` 

* Disable default site

```
sudo a2dissite sudo a2dissite 000-default-conf
```

* Reload apache2 service

```
sudo systemctl reload apache2
```

## Add wordpress dependencies

* [Wordpress - setup](https://www.digitalocean.com/community/tutorials/how-to-install-wordpress-on-ubuntu-22-04-with-a-lamp-stack)

```
sudo apt install php-curl php-gd php-mbstring php-xml php-xmlrpc php-soap php-intl php-zip
```

## Custom Apache config for Wordpress

```

```

