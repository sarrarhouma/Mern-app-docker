# Déploiement d'une application MERN avec Docker

## Objectifs
- Containeriser une application MERN (MongoDB, Express, React, Node.js) avec Docker.
- Utiliser Docker Compose pour orchestrer plusieurs conteneurs.

## Structure du projet
- **client/** : Application React.
- **server/** : API Express.

## Instructions

### Prérequis
- Docker et Docker Compose installés.

### Étapes
1. Cloner le projet :
   ```bash
   git clone https://gitlab.com/devops_tps/mern-app
   cd mern-app
Construire les images Docker :

Serveur :
cd server
docker build -t mern-server .
Client :
cd client
docker build -t mern-client .
Créer un réseau Docker :

docker network create mern-network
Lancer MongoDB :

docker run -d --name mongodb --network mern-network mongo
Lancer les conteneurs serveur et client :

docker run -d --name server --network mern-network -p 9000:9000 mern-server
docker run -d --name client --network mern-network -p 3000:3000 mern-client
Utiliser Docker Compose pour automatiser le processus :

docker compose up --build
Résultat
Accédez à l'application client sur http://localhost:3000.
L'API serveur est disponible sur http://localhost:9000.
![image](https://github.com/user-attachments/assets/59e79afe-a6cb-4873-95d3-b8ee681b7da8)
