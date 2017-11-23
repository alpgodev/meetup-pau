# meetup-pau
Meetup ML Pau - Optimisation distribuée

## Résumé 

Quand on utilise des algorithmes de Machine Learning on doit résoudre un problème d’optimisation pour estimer les paramètres du modèle. Ces méthodes d’optimisation sont souvent des boîtes noires pour les utilisateurs et leur fonctionnement reste invisible. L’objectif de ce meetup est de démystifier ces méthodes, en particulier lorsqu’on a énormément de données ou/et beaucoup de paramètres (Big Data). 

Une première partie présentera comment on peut résoudre un problème d’optimisation en grande taille en utilisant la puissance de plusieurs machines (cluster). Ensuite, comme ce meetup se place sous le signe de l’action nous développerons ensemble (en Python) une méthode d’optimisation distribuée à travers le framework Spark sur un cas d’application pratique.

Références : 
Spark - http://spark.apache.org
Docker - http://www.docker.com

## Quelques préparatifs pour la partie pratique du Meetup du 20 décembre 2017 “

Lors de la partie pratique nous utilisons le framework Spark en mode local (c’est-à-dire avec un noeud) sur un jeu de données de petite taille. Cependant, le code (Python) développé lors de la séance pourra être testé avec un gros jeu de données sur un cluster Spark - i.e. avec un service cloud dédié (AWS, Microsoft Azure, Google Cloud, IBM CC Labs, …) ou un cluster privé.

Pour cette partie pratique nous utiliserons une image Docker qui contient les outils et librairies nécessaires (Python, Notebook Jupyter, Spark …). 

Docker est un gestionnaire d’images qui permet de virtualiser une machine. Il utilise les librairies de votre système pour allouer dynamiquement des ressources pour une instance de l’image, appelée “container“. Il reste plus léger qu’une machine virtuelle standard. Docker est disponible pour Windows, MacOS et Linux.

1 . installation de docker

Premièrement, rendez-vous sur le site officiel de docker pour télécharger l'outil d'installation nécessaire à votre distribution :
	•	Mac : http://store.docker.com/editions/community/docker-ce-desktop-mac
	•	Windows : http://store.docker.com/editions/community/docker-ce-desktop-windows
	•	Linux : http://www.docker.com (Get Docker)

Lorsque l’installation est terminée, vérifiez votre installation en lançant la commande (dans un Terminal): docker run hello-world
Si vous obtenez le message suivant c’est que l’installation est réussie et que Docker peut charger et exécuter des images.

Hello from Docker!
This message shows that your installation appears to be working correctly.

To generate this message, Docker took the following steps:
 1. The Docker client contacted the Docker daemon.
 2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
 3. The Docker daemon created a new container from that image which runs the
    executable that produces the output you are currently reading.
 4. The Docker daemon streamed that output to the Docker client, which sent it
    to your terminal.

To try something more ambitious, you can run an Ubuntu container with:
 $ docker run -it ubuntu bash

Share images, automate workflows, and more with a free Docker ID:
 https://cloud.docker.com/

For more examples and ideas, visit:
 https://docs.docker.com/engine/userguide/

2. Téléchargement des données et du TP (notebooks Jupyter)

Rendez-vous à cette adresse pour récupérer les données et les notebooks: 

Sur votre machine créer un répertoire notebooks

2. Installation de l’image 

À présent nous allons charger et lancer l’image qui sera utilisée lors des travaux pratiques.

docker run -it --rm -p 8888:8888 -p 4040:4040 -v $(pwd)/notebooks:/home/jovyan/work jupyter/all-spark-notebook:latest

Note - La première fois que vous utiliserez cette commande, l'image sera chargée, ce qui nécessite un certain temps de téléchargement (environ 4Go).

3. Ouvrir votre navigateur avec le lien : http://localhost:8888/

4. 
