# Host-a-Wordpress-Website-on-AWS-EC2-with-own-domain-name

Install apache and mysql

```
sudo apt install apache2 -y && sudo apt install mysql-server -y 
```

First, install the application dependencies you need for WordPress. In your terminal, run the following command.

```
sudo apt install php libapache2-mod-php php-mysql -y
```

Download wordpress and extract 

```
wget https://wordpress.org/latest.tar.gz
tar -xzf latest.tar.gz
```

now go to wordpress dir and change some config

```
$ cd wordpress
$ cp wp-config-sample.php wp-config.php
$ nano wp-config.php
```

Finally, create a database user for your WordPress application and give the user permission to access the wordpress database.

Run the following commands in your terminal:

```mysql
CREATE DATABASE wordpress;
CREATE USER 'wordpress' IDENTIFIED BY 'wordpress-pass';
GRANT ALL PRIVILEGES ON wordpress.* TO wordpress;
FLUSH PRIVILEGES;
Exit
```
