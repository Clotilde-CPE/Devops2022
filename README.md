# Devops2022

Commandes importantes : 
Docker :
docker ps / docker ps -a
docker images
docker rm -f backend
docker run -p 8080:8080 --network appnetwork --name backend backend
docker buid -t backend
docker-compose up -d
docker-compose ps
docker tag database clotilde4923710/database:1.0
docker push clotilde4923710/database:1.0
Ansible :
ansible all -i inventories/setup.yml -m ping
ansible all -i inventories/setup.yml -m setup -a "filter=ansible_distribution*"
ansible all -i inventories/setup.yml -m yum -a "name=httpd state=absent" --become
ansible-playbook -i inventories/setup.yml playbook.yml

1-1 Document your database container essentials: commands and Dockerfile
- voir commentaires dans le Database/Dockerfile
- 01-CreateScheme.sql : créé 2 tables avec leur clé primaire dans la base de donnée
- 02-InsertData.sql : insère des données dans la base de donnée

1-2 Why do we need a multistage build ? And explain each steps of this dockerfile
- Nous devons utiliser un multistage build car nous devons utiliser plusieurs FROM avec des bases différentes, pour n'avoir que les fichiers désirés dans l'image finale
- voir commentaires dans le simple-api/Dockerfile

1-3 Document docker-compose most important commands
1-4 Document your docker-compose file
- voir commentaires dans le docker-compose.yml
 
1-5 Document your publication commands and published images in dockerhub
docker tag database clotilde4923710/database:1.0 //tag l'image database
docker push clotilde4923710/database:1.0 //push cette l'image database sur dockerhub
docker tag backend clotilde4923710/backend:1.0 //tag l'image backend
docker push clotilde4923710/backend:1.0 //push cette l'image backend sur dockerhub
docker tag httpd clotilde4923710/httpd:1.0 //tag l'image httpd
docker push clotilde4923710/httpd:1.0 //push cette l'image httpd sur dockerhub

2-1 What are testcontainers?
Ce sont des librairies Java qui permettent de lancer nombreux conteneurs en essai.

2-2 Document your Github Actions configurations
voir .main.yml

2-3 Document your quality gate configuration
voir .main.yml

3-1 Document your inventory and base commands
voir setup.yml
