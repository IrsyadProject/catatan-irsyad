# Link Referensi Settingan Web Server

<p>Sistem Operasi menggunakan Ubuntu Server 22.04 Jemmy, Berikut Ini Adalah Linknya:</p>
<ul>
    <li><a href="https://www.digitalocean.com/community/tutorials/how-to-install-mariadb-on-ubuntu-22-04">Install MariaDB in Ubuntu 22.04</a></li>
    <li><a href="https://www.digitalocean.com/community/tutorials/how-to-install-nginx-on-ubuntu-22-04">Install Nginx in Ubuntu</a></li>
    <li><a href="https://www.digitalocean.com/community/tutorials/how-to-install-git-on-ubuntu-22-04">Install Git</a></li>
    <li><a href="https://github.com/nodesource/distributions">Install Nodejs</a></li>
    <li><a href="https://www.digitalocean.com/community/tutorials/how-to-install-node-js-on-ubuntu-22-04">Install Nodejs by Digitalocean</a></li>
</ul>

# Contoh Konfigurasi Nginx

<p>Berikut ini codenya:</p>

```
server {
	listen 80 nameserver;
    root /var/www/html;

    # Add index.php to the list if you are using PHP
    index index.php index.html index.htm;

    location / {
    	try_files $uri $uri/ /index.php;
    }

    location ~ \.php$ {
    	include snippets/fastcgi-php.conf;
    	fastcgi_pass unix:/var/run/php/php8.1-fpm.sock;
    }

    location ~ /\.ht {
    	deny all;
    }

    location = /composer.json {
    	deny all;
    }

    location = /package.json {
    	deny all;
    }

    location = /package-lock.json {
    	deny all;
    }

}

```
