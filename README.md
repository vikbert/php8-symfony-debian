# php8-symfony-debian
Stack LAMP : Debian 11, PHP8, MYSQL, Apache, Phpmyadmin, Symfony cli, Composer.

Prerequis installer Docker via Docker Compose:
- **[Docker](https://docs.docker.com/get-docker/)**
- **[Docker-compose](https://docs.docker.com/compose/install/)**

Getting started :
```
git clone https://github.com/vikbert/php8-symfony-debian.git
```
```
cd php8-symfony-debian
```

```
docker-compose up -d
```

→ List the containers :
```
docker ps 
```

```
docker exec -ti php-apache bash
```

→ Create symfony project (https://symfony.com/doc/current/setup.html) exemple :
```
symfony new my_project_name --full
```
```
cd my_project_name
```

→ Config user
```
adduser username
chown username:username -R .
```

→ Build-in web server
```
symfony serve -d
```
```
exit
```
## licence
MIT [@vikbert](https://vikbert.github.io/)
