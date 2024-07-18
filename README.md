# Docker

## Docker Cheat Sheets

- https://docs.docker.com/get-started/docker_cheatsheet.pdf
- https://dockerlabs.collabnix.com/docker/cheatsheet/

## Comandos mais utilizados

**Build**

*Imagem Laravel*

```docker build -t patrickmarques/laravel:prod . -f Dockerfile.prod```

*Imagem Ngnix*

```docker build -t patrickmarques/ngnix:prod . -f Dockerfile.prod```

**Network**

*Rede para Proxy com Ngnix*

```docker network create  laranet-patrick```

**Container**

*Imagem Laravel Alpine*

```docker run -d --network laranet-patrick --name patrick-laravel patrickmarques/laravel:prod```

*Imagem Nginx Alpine*

```docker run -d --network laranet-patrick --name patrick-ngnix -p 8080:80 patrickmarques/ngnix:prod```

*Imagem Ubuntu*

```docker run -it -d --network laranet-patrick --name patrick-ubuntu ubuntu```

*Executar bash ubuntu*

```docker exec -it patrick-ubuntu /bin/bash```