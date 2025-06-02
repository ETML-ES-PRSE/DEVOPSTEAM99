# Web Server

## Pre-requisites

* Update the repositories' package list

```
sudo apt update
```

* Install Apache (standard installation)

```
sudo apt install apache2
```

## Backlog

## Acceptance criteria

### Exposes port 8000

* Open the port config file
   
```
sudo vi /etc/apache2/port.conf
```

* Update the port

```
Listen 8000
```

* Reload Apache

```
sudo systemctl reload apache2
```

* Test

```
curl localhost:8000
```

### Requirements for wordpress (latest version)

### Log active and clean (access, error)

### Apache is a service

### Use of vhost
runs with restricted permissions

