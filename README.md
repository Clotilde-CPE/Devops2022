# Devops2022

à retenir : 
docker run -p 8080:8080 --network appnetwork --name backend backend
docker buid -t backend
docker-compose up -d

1-1 Document your database container essentials: commands and Dockerfile
- Voir commentaires dans le Database/Dockerfile
- 01-CreateScheme.sql : créé 2 tables avec leur clé primaire dans la base de donnée
- 02-InsertData.sql : insère des données dans la base de donnée

1-2 Why do we need a multistage build ? And explain each steps of this dockerfile
- Nous devons utiliser un multistage build car nous devons utiliser plusieurs FROM avec des bases différentes, pour n'avoir que les fichiers désirés dans l'image finale
- Voir commentaires dans le simple-api/Dockerfile
