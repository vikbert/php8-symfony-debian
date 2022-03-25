# php8-symfony-debian
Installation d'un environnement de développement pour Symfony avec Docker qui comprend une stack LAMP : Debian 11, PHP8, MYSQL, Apache, Phpmyadmin, Symfony cli, Composer.

Pré-requis installer Docker et Docker Compose:
- **[Docker](https://docs.docker.com/get-docker/)**
- **[Docker-compose](https://docs.docker.com/compose/install/)**
- Pour utiliser Docker sans sudo (optionnel pas securisé) : https://docs.docker.com/engine/install/linux-postinstall/

Installer l'environnement de dev :
```
git clone https://github.com/vikbert/php8-symfony-debian.git
```
```
cd php8-symfony-debian
```

→ Construire les images et démarrer les containers en arrière plan (utiliser --build pour re builder les images) Par defaut utiliser sudo sous linux:
```
docker-compose up -d
```

→ Lister vos containers actifs :
```
docker ps 
```

Le nom du container qui contient php et apache a pour nom : "php-apache" comme défini dans le docker-compose.yml  :

→ Lancer le bash de notre conteneur php afin d'intéragir avec la machine Debian :
```
docker exec -ti php-apache bash
```

→ Creer son nouveau projet symfony (https://symfony.com/doc/current/setup.html) exemple :
```
symfony new my_project_name --full
```
```
cd my_project_name
```

→ Donner les droits à tout le repertoire, remplaçer username par le meme nom que notre session locale
```
adduser username
chown username:username -R .
```

→ Lancer le serveur interne de Symfony en arrière plan :
```
symfony serve -d
```

→ On peut donc lancer les commandes de Symfony, composer ou php bin/console et pour sortir du bash tapez : 
```
exit
```
## licence
MIT [@vikbert](https://vikbert.github.io/)
