# MySQL Setup for Wordpress

## Create WordPress DATABASE

```
mysql -u root -p
```

```
CREATE DATABASE wordpress DEFAULT CHARACTER SET utf8 COLLATE utf8_unicode_ci;
```

## Enable native password plug-in

Note : you may need to enable plugin authentication

* [MySQL - Native password not loaded](https://php.watch/articles/fix-php-mysql-84-mysql_native_password-not-loaded)

```
# /etc/mysql/conf.d/enable-mysql-native-password.cnf
# Enable mysql_native_password plugin
[mysqld]
mysql_native_password=ON
```

## Create WordPress User

```
CREATE USER 'wordpressuser'@'%' IDENTIFIED WITH mysql_native_password BY 'password';
```

* % -> must be replaced by the wordpress instance ip 10.0.X.12
* 'password' -> must be replaced to satisfy the policy requirements

## Test connectivity from Wordpress instance

* Install Official MySQL Client from Oracle APT Repo (for MySQL 8.x)

```
wget https://dev.mysql.com/get/mysql-apt-config_0.8.29-1_all.deb
```

* Install the APT Config Package:

```
sudo dpkg -i mysql-apt-config_0.8.29-1_all.deb
```

* Update the mysql-client

```
sudo apt update
sudo apt install mysql-client
```
