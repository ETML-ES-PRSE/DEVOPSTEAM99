# MySQL Setup for Wordpress

```
mysql -u root -p
```

```
CREATE DATABASE wordpress DEFAULT CHARACTER SET utf8 COLLATE utf8_unicode_ci;
```

```
CREATE USER 'wordpressuser'@'%' IDENTIFIED WITH mysql_native_password BY 'password';
```

* % -> must be replaced by the wordpress instance ip 10.0.X.12
* 'password' -> must be replaced to satisfy the policy requirements

* 
