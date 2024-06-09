
# Ecosystème Big Data dans docker

Environnement d'étude des principaux frameworks big data dans Docker.
<br> Cette configuration créera des dockers avec les frameworks HDFS, HBase, Hive, Presto, Spark, Jupyter, Hue, Mongodb, Metabase, Nifi, Kafka, Mysql et Zookeeper avec l'architecture suivante :
<br>

![Ecossistema](ecosystem.jpeg)

## LOGICIEL REQUIS
#### Pour créer et utiliser l'environnement, nous utiliserons git et Docker
 * Installation de Docker Desktop sur Windows [Docker Desktop](https://hub.docker.com/editions/community/docker-ce-desktop-windows) ou docker sur [Linux](https://docs.docker.com/install/linux/docker-ce/ubuntu/)
 *  [Installation de git](https://git-scm.com/book/pt-br/v2/Come%C3%A7ando-Instalando-o-Git)
   
## INSTALLATION
*REMARQUE : Cette étape ne doit être effectuée qu’une seule fois. Une fois l'environnement créé, utilisez docker-compose pour démarrer les conteneurs comme indiqué dans la rubrique DÉMARRAGE DE L'ENVIRONNEMENT*

#### Création du répertoire docker :
*REMARQUE : Créez un répertoire appelé docker*

 * Suggestion sous Windows :
 * Créer le répertoire docker à la racine de votre lecteur
 ex : C:\docker

 * Suggestion sur Linux :
 * Créer le répertoire dans le home de l'utilisateur
 ex : /home/utilisateur/docker

#### Dans un terminal/DOS, dans le répertoire docker, clonez le projet sur github
 git clone https://github.com/crystalloide/bigdata_docker.git

#### Dans le répertoire bigdata_docker, il y aura les objets suivants
![ls](ls.JPG)

   
## DÉMARRAGE DE L'ENVIRONNEMENT

 *Sous Windows, ouvrez PowerShell, sous Linux un terminal*

### Dans le terminal, dans le répertoire bigdata_docker, exécutez docker-compose
 docker compose up -d

### Vérifiez les images et les conteneurs

         docker image ls

![image docker ls](docker_image_ls.JPG)

         docker container ls

![conteneur docker](docker_container_ls.JPG)

## RÉSOUDRE LES PROBLÈMES

 *Sous Windows, ouvrez le terminal Docker Quickstart*

### Arrêter un conteneur
         docker stop [nom du conteneur]

### Arrêter tous les conteneurs
         docker stop $(docker ps -a -q)

### Supprimer un conteneur
         docker rm [nom du conteneur]

### Supprimer tous les conteneurs
         docker rm $(docker ps -a -q)

### Données du conteneur
         docker container inspect [nom du conteneur]

### Démarrer un conteneur
         docker-compose up -d [nom du conteneur]

### Démarrer tous les conteneurs
         docker-compose up -d 

### Accéder à la log d'un conteneur
         docker container logs [nom du conteneur] 

## Accès à l'interface Web des frameworks (Web UI)
 
* HDFS *http://localhost:50070*
* Presto *http://localhost:8080*
* Hbase *http://localhost:16010/master-status*
* Mongo Express *http://localhost:8081*
* Kafka Manager *http://localhost:9000*
* Metabase *http://localhost:3000*
* Nifi *http://localhost:9090*
* Jupyter Spark *http://localhost:8889*
* Hue *http://localhost:8888*
* Spark *http://localhost:4040*

## Accès via un shell

   ##### HDFS

          docker exec -it datanode bash

   ##### HBase

          docker exec -it hbase-master bash

   ##### Sqoop

          docker exec -it datanode bash
        
   ##### Kafka

          docker exec -it kafka bash

## Accès JDBC 

   ##### MySQL
          jdbc:mysql://database/employees

   ##### Hive

          jdbc:hive2://hive-server:10000/default

   ##### Presto

          jdbc:presto://presto:8080/hive/default

## Utilisateurs et mots de passe

   ##### Hue
    Login utilisateur : admin
    Mot de passe : admin

   ##### Metabase
    Login utilisateur: bigdata@class.com
    Mot de passe: bigdata123 

   ##### MySQL
    Login utilisateur: root
    Mot de passe: secret
   
   ##### MongoDB
    Login utilisateur: root
    Mot de passe: root
    Database d'Authentication : admin

## Images   

[Docker Hub](https://hub.docker.com/u/fjardim)

## Documentation officielle

* https://zookeeper.apache.org/
* https://kafka.apache.org/
* https://nifi.apache.org/
* https://prestodb.io/
* https://spark.apache.org/
* https://www.mongodb.com/
* https://www.metabase.com/
* https://jupyter.org/
* https://hbase.apache.org/
* https://sqoop.apache.org/
* https://hadoop.apache.org/
* https://hive.apache.org/
* https://gethue.com/
* https://github.com/yahoo/CMAK
* https://www.docker.com/
