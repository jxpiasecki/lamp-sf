## Linux Apache Mysql Php for Symfony © 2021

### Navigate

- Application:
    - [http://localhost](http://localhost)
    - [http://localhost:8101](http://localhost:8101)
    - [http://lamp.sf.localhost:8101](http://lamp.sf.localhost:8101)
    - [http://lamp.sf.localhost:80](http://lamp.sf.localhost:80)
    - [https://lamp.sf.localhost](https://lamp.sf.localhost)
- PhpMyAdmin:
    - [http://localhost:8102](http://localhost:8102)
    - [http://db.lamp.sf.localhost:8102](http://db.lamp.sf.localhost:8102)

### Initialize SF project

```
cd ./lamp-sf
rm -rf ./codebase
composer create-project symfony/website-skeleton codebase
sudo chmod -R og+rw lamp-sf/
sudo chown -R jarek:jarek lamp-sf/
```

### DB connection string

- Run on docker container: ```docker exec -it --user www-data lamp_sf-server bash```
```
echo $DATABASE_URL
```
- Output like
```
mysql://app_user:t3rceS@db_server:3306/lamp_sf?serverVersion=10.5
```

### Credits to

[LAMP Docker setup with PHP 8 and MariaDB for Symfony projects](https://www.bornfight.com/blog/blog-lamp-docker-setup-with-php-8-and-mariadb-for-symfony-projects/)