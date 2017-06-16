# TechView


## Introduction

`TechView` is a web application that aims to be the wiki page of technical interview questions.

Its backend is built with python Flask framework and the frontend is using Bootstrap framework.

## Information

IP address: `52.34.113.93`

SSH port: `2200`

SSH key: `/home/grader/.ssh/authorized_keys`

URL: `http://52.34.113.93/`

Software installed
* Apache2
* Postgresql
* Python2

## Configuration

```
<VirtualHost *:80>
        ServerName catalog
        ServerAdmin lei@commitlogs.com

        WSGIDaemonProcess webtool user=www-data group=www-data threads=5 home=/var/www/catalog/
        WSGIScriptAlias / /var/www/catalog/catalog.wsgi
        <Directory /var/www/catalog/catalog/>
                WSGIProcessGroup catalog
                WSGIApplicationGroup %{GLOBAL}
                WSGIScriptReloading On
                Order allow,deny
                Allow from all
        </Directory>
        Alias /static /var/www/catalog/catalog/static
        <Directory /var/www/catalog/catalog/static/>
                Order allow,deny
                Allow from all
        </Directory>
        ErrorLog ${APACHE_LOG_DIR}/error.log
        LogLevel info
        CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>
```
