---
layout: post
title: Docker containers
published: true
---

Meetup sur docker dans les locaux de Comet. 


Aymen nous fait un panorama de systèmes de containers avant Docker depuis les  années 80. Puis il nous détaille la mise à l'échelle impressionnante de la communauté open source vite rejoint par les géants du Web comme Google, Aamzon... 
Enfin il passe en revue des outils de la communauté, qui sont intéressants de tester.
Et replace en perspective l'importance de l'orchestration et de Kubernetes presque aussi important que le conteneur lui-même.


Par Aymen El Amri
CEO de eralabs.io / Dev ops Services
Twitter @eon01
Site personnel http://www.aymenelamri.com
De la communauté de http://devopslinks.com


## Les containeurs existent depuis les années 1980

Docker n'est pas le  premier système de conteneurs. Chroot jail le premier système basé sur les conteneurs date de 1979!

* Chroot Jail
* CGroups
* LXC : linux container
* LMCTFY by Google Let Me Contain That for You Tout tourne sur des conteneurs chez google !
* Docker en 2013 : le plus populaire jusqu'à maintenant car plus developer friendly. Plus simple à configurer
* RKT Rocket : plus sécurisé et standardisé 

## Mais qu'est ce qui fait la force de docker

Docker permet à des développeurs de manipuler des ressources de Dev ops, sans la complexité. 

Containers vs VMs

Docker est beaucoup plus léger car il ne comprend pas l'OS. 


### Architecture de Docker 

* Docker entreprise Edition 
* Docker community Edition 
* Swarm : Orchestration 
* containerd : Container Runtime

### Docker tools 

* **Docker engine**: Le logiciel docker
* **Docker compose**: On veut installer LAMP, on créait 3 conteneurs, pour PHP, MYSQL et PHP Docker compose permet de lier les 3 conteneurs qui définisent ces trois conteneurs
* **Docker Machine**: Permet de créer des machines virtuelles auto-executable, générer des images sur Amazon...


### Evolution de Docker

* **LXC***: A la base il se basait sur LXC
* **LibContainer**: Puis ils ont développé leur propre système de conteneur libcontainer Permet d'accéder aux linux facilities... qui touchent à l'isolation et à la securité
* **RunC** : En 2015, développement de RunC, le developpement est open source, mais soutenu par des grands, google... Abstraction entre la communication entre le conteneur et un runtime
* **ContainerD** en 2016 permet de faire de la supervision des processus 
* Passage d'une architecture monolytique à une architecture par composants
* 2017, les containeur sont devenus mainstream, google cloud, amazon, Aws ...
* **Moby project**: permet de modulariser le développement de docker

### Les composants de MOBY

* **ContainerD**: gère le cycle de vie
* **LinuxKit**: permet de créer des distributions linux à partir d'un fichier yaml. Permet de créer des machines virtuelles pour des clouds publics comme celui d'AMAZON
* **InfraKit**: Déclaratif desired state, on ne décrit pas les actions, mais l'état que l'on veut attendre
* **SwarmKit**: Orchestrer des système distribués

### L'importance de l'orchestration 

Swarm vs Kubernetes
Kubernetes est inclus nativement comme swarm on peut choisir son orchestration. Indispensable pour mettre en production.

* **Docker Swarm**: simple à utiliser et inclu dans docker. Bien pour commencer
* **Kubernetes**: Plus complexes mais leader du marché de l'orchestration. Utilisé par github, wikimedia
* **Mesos**: Utilisé par netflix, twitter...

Service cloud kubernetes : GKE de google / amazon ECS (la version amazon) et EKS (Kubernetes) / Azure ACS 
Cloud alibaba 
Cloud Redhat


### Les questions 

* Quel est le meilleur site pour commencer ? 

Le site de docker est bien pour commencer, Docker Academy... jusqu'à Swarm. Pour Kubernetes il faut passer à autre chose.

* Je ne suis pas devops mais dev, j'utilise docker compose en prod. Est ce que Swarm est utilisable en prod. 

Pour une application très simple avec une api en node js et le front sur front. Le Docker swarm permet de faire un cluster  avec le front et le back.

* Est ce que docker swarm a un réel overhead sur les pefs par rapport à une install native

Un container par machine virtuelle sans orchestration c'est du gaspillage. Avec de l'orchestration, on peut mettre beaucoup de conteneurs sur la même machine. Ils peuvent communiquer à travers un reseau interne, ou si si plusieurs machines, récréer un lien virtuel entre tout ces conteneurs sur plusieurs machines. 


* **Traffic** permet de gérer des micro-services. Les micro-services sont moins en vogue et rejoignent les conteneurs, car ils  partagent les mêmes concepts, la découverte...

* **Le futur du conteneur**: stateless et serverless

*  **La base de donnée dans un conteneur**: Pas le plus simple, et pas dans la logique stateless. Plus simple d'avoir une base de donnée dans le clouds, le faire avec des conteneurs moins simple. 
Une intervention d'un développeur: la base de donnée peut être mis dans un container, mais la data elle-même est mis sur le host du container. L'avantage de mettre la base de donnée dans un containeur permet de mettre à jour la version de base de donnée, très simplement....







