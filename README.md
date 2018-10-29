## Start app ##
user@VM:/opt/from-zero-to-docker$ docker-compose up -d

## Check logs ##
user@VM:/opt/from-zero-to-docker$ docker-compose logs -f

## Clean all: images + container + volumes ##
user@VM:/opt/from-zero-to-docker$ docker-compose down
Stopping fromzerotodocker_app_1 ... done
Stopping fromzerotodocker_db_1  ... done
Removing fromzerotodocker_app_1 ... done
Removing fromzerotodocker_db_1  ... done
Removing network fromzerotodocker_default
user@VM:/opt/from-zero-to-docker$ docker volume rm `docker volume ls -q | grep fromzerotodocker`
fromzerotodocker_app_logs
fromzerotodocker_db_data
user@VM:/opt/from-zero-to-docker$ docker rmi `docker images | grep fromzerotodocker | cut -d' ' -f1`
Untagged: fromzerotodocker_app:latest
Deleted: sha256:8120e58144546a5a79e9b9d449a00f3da6fc9493c403846d0dad411727897299
Deleted: sha256:cbe099e3042803f41523f2375789d2796b9d5b272fd1652201726bee2d514e88
Deleted: sha256:b9af11950a4f8c96e0ac6a2031d9286a91072bad2e0a4731a8706fedf8943267
Deleted: sha256:9c72b2a0bf26cafe0855fe7e6b6960c36af5c87a47743a75fab871c43bf6b500
Deleted: sha256:27e35f0f0c9b7ede4967e4d2399af0d1e87dd5810f8f82039b3ea3baff83cc0d
Deleted: sha256:023ac72cf23f679a26d8d89878dcc344082d8fbe4e8ffd604e25461073649f37

## Accounts ##
- p4997 - ROLE: Coordenador de TFCs
- p5617 - ROLE: Professor
- a111 - ROLE: Aluno
- a112 - ROLE: Aluno

## Access and navigate inside mysql database ##
user@VM:/opt/from-zero-to-docker$ docker exec -it fromzerotodocker_db_1 bash
root@c0f276bdd624:/# mysql -u gestaotfc -ptfc
mysql: [Warning] Using a password on the command line interface can be insecure.
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 10
Server version: 5.7.23 MySQL Community Server (GPL)

Copyright (c) 2000, 2018, Oracle and/or its affiliates. All rights reserved.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.


mysql> use gestaotfc
Reading table information for completion of table and column names
You can turn off this feature to get a quicker startup with -A

Database changed
mysql> show tables
