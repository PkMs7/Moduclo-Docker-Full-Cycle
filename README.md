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