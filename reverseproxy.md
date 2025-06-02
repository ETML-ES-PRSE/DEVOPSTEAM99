# Reverse proxy

## Pre-requisites

* Update the repositories' package list

```
sudo apt update
```

* Install Nginx (standard installation)

```
sudo apt install nginx
```

## Backlog

---

### Nginx is a service (automatic restart)

```
systemctl status nginx
```

### Active, clean logs

* Identify logs location
```
ls -la /var/log/nginx/
```

* Read access.log
```
sudo tail -f /var/log/nginx/access.log
```

* Read error.log

```
sudo tail -f /var/log/nginx/error.log
```

### Exposes port 8080

* Open the default host config
  
```
sudo vi /etc/nginx/sites-enabled/default
```

* Update the port

```
server {
        listen 8080 default_server;
        listen [::]:8080 default_server;
        [...]
```

* Reload Nginx

```
sudo systemctl reload nginx
```

* Test

```
curl localhost:8080
```

### Nginx service is run with restricted permissions

---
//TODO
---

### Url redirection to ip address

### Use of a vhost

### Redirects to wordpress on port 8000
