
# 1. Image de base
FROM node:lts-alpine

# 2. Répertoire de travail
WORKDIR /app

# 3. Copier les fichiers package.json et package-lock.json
COPY package*.json ./

# 4. Installer les dépendances
RUN npm install

# 5. Copier le reste des fichiers React
COPY . .

# 6. Définir l'URL de l'API
ARG REACT_APP_API_URL
ENV REACT_APP_API_URL=$REACT_APP_API_URL

# 7. Construire l'application React
RUN npm run build

# 8. Installer le serveur HTTP
RUN npm install -g serve

# 9. Exposer le port 3000
EXPOSE 3000

# 10. Démarrer le serveur HTTP
CMD ["serve", "-s", "build", "-l", "3000"]