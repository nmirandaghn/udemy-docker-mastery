## Section 3
1. Install Docker Desktop
2. In VSCode install Docker, Kubernetes and Remote Development extensions

## Section 4
Lesson 19 - Basic Commands
19. CLI commands
  19.1. docker version
  19.2. docker info
  19.3. docker container run --publish 80:80 nginx
  19.4. docker container run --publish 80:80 --detach nginx
  19.5. docker container run --publish 80:80 --detach nginx
  19.6. docker container run --publish 80:80 --detach --name myhost nginx
  19.7. docker container ps
  19.8. docker container ls
  19.9. docker container ls -a # List all the containers
  19.10. docker container stop <container>
  19.11. docker container rm <container>
  19.12. docker container rm -f <container>
  19.13. docker top <container>
  19.14. docker start <container>
  19.15. docker container logs <container>

Lesson 24 - CLI Process Monitoring
24.1. docker container stats
24.2. docker container inspect

Lesson 26 - Getting a Shell Inside Containers: No Need for SSH
26.1.  docker exec -it mariadb mariadb -u root -p<admin1234> # Se conecta a la bd mariadb indicando la clave de root para acceder
26.2. docker exec -it mysql mysql -u root -p # Se conecta a la bd mysql solicitando la clave de root para acceder
26.3. docker exec -it nginx bash # Ejecuta bash en el container nginx
26.4. docker container start -ai <container> # Inicia contenedor con interactivo
26.6 docker container start --help
26.7 docker container exec --help
26.8. docker image ls

docker run: Crea y arranca un contenedor nuevo (usado la primera vez que inicias la base de datos).
docker exec: Ejecuta un comando en un contenedor ya existente (usado para interactuar con una base de datos ya creada).

Lesson 27
27.1. docker container port <name>
27.2. docker container inspect --format '{{ .NetworkSettings.IPAddress}}' <name>

Lesson 29 - Virtual Networks
29.1. docker network ls
29.2. docker network inspect bridge
29.3. docker network create my-app-net
29.4. docker run -d --name new-nginx --network my-app-net nginx
29.5. docker network inspect my-app-net
29.6. docker network connect <network> <container>
29.7. docker network disconnect <network> <container>

Lesson 35 - Robin Test
35.1. docker network create dude 
35.2. docker container run -d --net dude --net-alias search elasticsearch:2
35.2. docker container run --rm --net  dude alpine nslookup search

## Section 5 - Container Images
Lesson 37 - Docker Images
37.1. docker image pull <image>##
37.2. docker image ls # List local images

Lesson 38 - Images Layer and History
38.1. docker image history <image>
38.2. docker image inspect <image>

Lesson 39 - Tags
39.1. docker image tag nginx nmiranda/nginx
39.2. docker image push nmiranda/nginx
39.3. docker login 
39.4. docker logout

Lesson 42. Building Images
42.1. docker image build -t nginx-with-html .

## Section 6
Lesson 47 - Volumes
47.1. docker volume ls
47.2. docker container run -d --name mysql_0 -e MYSQL_ALLOW_EMPTY_PASSWORD=True -v mysql-db:/var/lib/mysql  mysql # Create named volume
47.2. docker volume create <volume>

Lesson 49 - Bind Mounting
49.1. docker container run -d --name nginx_0 -p 80:80 -v $(pwd):/usr/share/nginx/html nginx

## Section 7

