# Utilisation de l'image Node.js alpine
FROM node:lts-alpine

# Définir le répertoire de travail
WORKDIR /app

# Copier les fichiers package*.json et installer les dépendances
COPY package*.json ./
RUN npm install

# Copier le reste des fichiers du serveur
COPY . .

# Exposer le port 9000
EXPOSE 9000

# Définir la variable MONGO_URI
ENV MONGO_URI=mongodb://mongodb:27017/mern-database

# Lancer l'application
CMD ["npm", "start"]
