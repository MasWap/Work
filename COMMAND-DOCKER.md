
<i>Created by Lilian DevOps of Algo.solutions</i>

# Commandes Docker

## <div  id="sommaire">./Sommaire :</div>

  

Ce fichier répertorie les différentes commandes et leur définition pour l'utilisation de Docker.

  

<hr>

  

##  <div  id="definition">./Commandes & Explications :</div>

| Installer Docker |
|------------------|

```bash
$ -> sudo apt-get install docker.io
```
<hr>

| Afficher les commandes Docker |
|------------------|

```bash
$ -> docker
```
<hr>

| Lister les conteneurs lancer sur la machine |
|------------------|

```bash
$ -> docker ps
OU
$ -> docker ps -a
```
<hr>

| Lancer un conteneur avec une image présente sur DockerHub |
|------------------|

```bash
$ -> docker run -di --name NomConteneur alpine:latest
```

<hr>

| Se connecter au conteneur |
|------------------|

```bash
$ -> docker exec -ti NomConteneur sh
```
<hr>

| Lancer un conteneur Nginx (Serveur web) |
|------------------|

```bash
$ -> docker run -tid -p 8080:80 --name NomConteneur nginx:latest
```
<hr>

| Accéder aux propriétés d'un conteneur (IP, ports, config...)|
|------------------|

```bash
$ -> docker inspect NomConteneur
```
<hr>

| Démarrer un conteneur|
|------------------|

```bash
$ -> docker start NomConteneur
```
<hr>

| Stopper un conteneur|
|------------------|

```bash
$ -> docker stop NomConteneur
```
<hr>

| Supprimer un conteneur en marche|
|------------------|

```bash
$ -> docker rm -f NomConteneur
```

| Modifier index.html du serveur web Nginx|
|------------------|

```bash
#Entrer dans le conteneur
$ -> docker exec -ti NomConteneur sh

#Update les packets & installer VIM
$ -> apt-get update
&
$ -> apt-get install vim

#Accéder au fichier index.html
$ -> vim usr/share/nginx/html/index.html
```
<hr>

| Créer un lien entre la machine local et le conteneur |
|------------------|
```bash
$ -> docker run -tid -p 8080:80 -v /srv/data/nginx:/usr/share/nginx/html --name web nginx:latest
```
<hr>

| Info sur les volume|
|------------------|

```bash
$ -> docker volume
```
<hr>

| Créer un volume|
|------------------|

```bash
$ -> docker volume create Nomvolume
```
<hr>

| Afficher les volumes|
|------------------|

```bash
$ -> docker volume ls
```
<hr>

| Informations sur un volume|
|------------------|

```bash
$ -> docker volume inspect NomVolume
```
<hr>

| Afficher les volumes|
|------------------|

```bash
$ -> docker volume ls
```
<hr>

| Créer un conteneur sur notre volume|
|------------------|

```bash
$ -> docker run -tid --name NomConteneur -p 8080:80 --mount source=NomVolume,target=/usr/share/nginx/html nginx:latest
```
<hr>

| Supprimer un volume (pensez à supprimer le conteneur avant de supprimer le volume)|
|------------------|

```bash
$ -> docker volume rm -f NomVolume
```
<hr>

| Afficher les images disponible sur la machine|
|------------------|

```bash
$ -> docker image ls
```
<hr>

| Créer une image|
|------------------|

```bash
$ -> docker commit -m "Création de mon image" IdDeMonConteneur NomImage:v1.0
```
<hr>

| Supprimer une image (Attention, supprimer le conteneur avant de supprimer l'image)|
|------------------|

```bash
$ -> docker image rm IdDeMonImage
```
<h1>

| Exemple de DockerFile (Ne pas oublier le point à la fin quand on créer le dockerfile)|
|------------------|

```bash
#Quand on est dans le conteneur, on fait
$ -> vim Dockerfile
&
$ -> docker build -t MonImage:version .

#Contenu du DockerFile
FROM ubuntu:latest
MAINTAINER NomMaintainer
RUN apt-get update \
&& apt-get install -y vim git \
&& apt-get clean \
&& rm -rf /var/lib/apt/lists/* /tmp* /var/tmp/*
```
<hr>

| Voir les séquences qui se sont exécuter sur une image|
|------------------|

```bash
$ -> docker history NomImage:MaVersion
```
<hr>

| Voir ce qu'il se passe sur une image|
|------------------|

```bash
$ -> docker diff NomImage
```
<hr>

| Activer ou désactiver le cache dans le Dockerfile|
|------------------|

```bash
#En ligne de commande
$ -> docker buil --no-cache -t test2 .
#Au niveau du RUN
RUN apk add --no-cache vim
OU
RUN apk add vim

#Pour optimiser le build de l'image, il faut mettre au plus 
#haut les variables déja stocker dans le cache, 
#comme cela ils ne sont pas re télécharger 
#lors du build de l'image.
```

# ./END
