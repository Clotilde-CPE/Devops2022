FROM postgres:11.6-alpine 
#défini l'image de base pour les instructions suivantes
COPY 01-CreateScheme.sql /docker-entrypoint-initdb.d
COPY 02-InsertData.sql /docker-entrypoint-initdb.d

ENV POSTGRES_DB=db \
POSTGRES_USER=usr \
POSTGRES_PASSWORD=pwd
#coordonnées pour se connecter à la BD
