# Database Engine

## Pre-requisites

* Update the repositories' package list

```
sudo apt update
```

* Add MySql dependencies
  
```
sudo apt install gnupg -y
```
  
### Install MySql (standard installation)

[Source](https://docs.vultr.com/how-to-install-mysql-on-debian-12)
         
## Update repositories
         
```
wget https://dev.mysql.com/get/mysql-apt-config_0.8.30-1_all.deb 
```

## Install the MySql Repository

```
sudo dpkg -i mysql-apt-config_0.8.30-1_all.deb
```

## Select MySql Installation

* Select "MySql Server & Cluster
