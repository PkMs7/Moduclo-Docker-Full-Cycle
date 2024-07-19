# Docker

## Docker Cheat Sheets

- https://docs.docker.com/get-started/docker_cheatsheet.pdf
- https://dockerlabs.collabnix.com/docker/cheatsheet/

## Comandos mais utilizados

**Build**

- *Imagem Laravel*

```docker build -t patrickmarques/laravel:prod pratica_docker_com_php/laravel/ -f pratica_docker_com_php/laravel/Dockerfile.prod```

- *Imagem Nginx*

```docker build -t patrickmarques/nginx:prod pratica_docker_com_nginx/nginx/ -f pratica_docker_com_nginx/nginx/Dockerfile.prod```

**Network**

- *Rede para Proxy com Ngnix*

```docker network create laranet-patrick```

**Container**

- *Imagem Laravel Alpine*

```docker run -d --network laranet-patrick --name laravel patrickmarques/laravel:prod```

- *Imagem Nginx Alpine*

```docker run -d --network laranet-patrick --name nginx -p 8080:80 patrickmarques/nginx:prod```

- *Imagem Ubuntu*

```docker run -it -d --network laranet-patrick --name patrick-ubuntu ubuntu```

- *Executar bash ubuntu*

```docker exec -it patrick-ubuntu /bin/bash```

# Docker-Compose

## Docker-Compose Cheat Sheets

- https://devhints.io/docker-compose

## Comandos mais utilizados containers

- *Executar bash aplicação*

```docker exec -it app bash```

- *Executar bash banco mysql*

```docker exec -it db bash```

## Comandos mais utilizados mysql

- *Entrar no banco*

```mysql -uroot -p```

- *Mostrar DBs criados*

```show databases;```

- *Criação da tabela exemplo da aplicação*

```use nodedb;```

```create table people(id int not null auto_increment, name varchar(255), primary key(id));```

```desc people;```