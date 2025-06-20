# Installation de Wordpress Debian
<p align ="center">
<img src="https://github.com/user-attachments/assets/687c397f-d999-4d7c-be7d-b6153a7a37cc" width=350>

```bash
$ sudo apt install apache2 -y
$ apt install mariadb-server -y
```
Configuration de la base de donnée du serveur
```bash
$ mysql_secure_installation
```
Ajout des modules php
```bash
$ apt install php libapache2-mod-php
$ apt install php php-pclzip php-mbstring php-soap php-mysql php-curl php-xml php-zip php-gd -y
```
Création de la base de données Wordpress
```bash
create database wordpress;

create user ‘wordpress’@’localhost’ identified by ‘wordpress’;

grant all privileges on wordpress.* to ‘wordpress’@’localhost’ with grant option;

flush privilèges;
```
Téléchargement de Wordpress
```bash
$ wget https://wordpress.org/latest.zip
```
```bash
$ tar -xvf "nom du fichier wordpress"
$ mv wordpress /var/www/html
```
Droit d'accées Wordpress
```bash
$ chown -R www-data:www-data /var/www/html/wordpress/
$ chmod -R 755 /var/www/html/wordpress/
````