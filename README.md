# ![Docker](https://user-images.githubusercontent.com/6461792/109390363-f782e680-78ef-11eb-9e79-a9e47d96e700.png)

# Comandos docker

Uma lista com alguns comandos do docker para o dia a dia :)

## Manupulando containers

- `docker ps -a`  Lista containers 
- `docker ps`  Lista todos os containers em execução
- `docker inspect <NOME ou ID>` inpeciona um container
- `docker stop <NOME ou ID>`  para um container
- `docker restart <NOME ou ID>`  reinicia um container
- `docker start <NOME ou ID>`  inicia um container
- `docker rm <NOME ou ID>`  remove um container
- `docker stats <NOME ou ID>`  verifica quanto recurso o container está consumido
- `docker top <NOME ou ID>`  verifica os processos que estão sendo executados no container
- `docker logs <NOME ou ID>`  visualiza os logs do container
- `docker run -d <IMAGEM>`  executa o container em segundo plano
- `docker run -p <PORTA_HOST>:<PORTA_CONTAINER> <IMAGEM>`  executa o container em segundo plano: Exemplo: docker run  -d -p 8080:80 nginx
- `docker run --name <NOME_DA_IMAGEM> <IMAGEM>`  nome para seu container
- `docker container prune`  remove todos os containers que estão parados
- `docker run --name <NOME_DA_IMAGEM> --link <CONTAINER> -d -p PORTA_HOST>:<PORTA_CONTAINER> <IMAGEM>`  linkando container. Exemplo: docker run --name blog_wordpress --link dbserver:mysql -d -p 8090:80 wordpress


## Manupulando imagens

- `docker images`  Lista as imagens 
- `docker rmi <NOME ou ID>`  remove uma imagem
- `docker commit <NOME ou ID> <NOME_DA_IMAGEM>`  gera uma imagem a partir de um container. Exemplo: docker commit b0ccb8cc6854 ngnix_default:v1

## Executar comandos dentro do container
- `docker exec <NOME ou ID> ls` lista pastas
- `docker exec -it <NOME ou ID> /bin/bash` acessa terminal do container

## Volumes
- `docker volume ls` lista todos os volumes
- `docker volume rm <NOME VOLUME>` remove um ou mais volumes
- `docker volume inspect <NOME VOLUME>` exibe informações volume
- `docker volume create <NOME VOLUME>` cria um volume
- `docker volume prune ` remove todos os volumes não usados
- `docker run -d -it -v /<PASTA>  <NOME ou ID IMAGEM>` cria um volume. Exemplo: docker run -d -it -v /data --name web04 nginx
- `docker run -d -p <PORTA_HOST>:<PORTA_CONTAINER> --name <NOME> -v /C/dev/:/usr/share/ngnix/html <IMAGEM>` compartilha volume. Exemplo: docker run -d -p 8087:80 --name web07 -v /c/dev/:/usr/share/nginx/html nginx
- `docker run -d -p <PORTA_HOST>:<PORTA_CONTAINER> --volumes-from <NOME ou ID> --name <NOME PARA O CONTAINER> <IMAGEM>` compartilha volume com container. Exemplo: docker run -d -p 8088:80 --volumes-from web07 --name web08 nginx

## Redes
- `docker network ls` lista todos as redes
- `docker network create --driver <DRIVER> <NOME>` cria uma rede. Exemplo: docker network create --driver bridge alpine-net
- `docker run -d --name <NOME_DA_IMAGEM> --network <NOME DA REDE> <IMAGEM>`  atribuindo um container a uma rede. Exemplo: docker run -d --name ngnix03 --network alpine-net nginx:alpine
- `docker network inspect <NOME/ID REDE> ` exibe informações de uma rede
- `docker network prune` remove todas as redes não usadas
- `docker network rm <NOME/ID REDE>` remove uma ou mais redes


## Contatos

[![Github Badge](https://img.shields.io/badge/-Github-000?style=flat-square&logo=Github&logoColor=white&link=https://github.com/wander4747)](https://github.com/wander4747)
[![Linkedin Badge](https://img.shields.io/badge/-LinkedIn-blue?style=flat-square&logo=Linkedin&logoColor=white&link=https://www.linkedin.com/in/wander-douglas/)](https://www.linkedin.com/in/wander-douglas/)
[![Whatsapp Badge](https://img.shields.io/badge/-Whatsapp-4CA143?style=flat-square&labelColor=4CA143&logo=whatsapp&logoColor=white&link=https://api.whatsapp.com/send?phone=5531993326096&text=Hello!)](https://api.whatsapp.com/send?phone=5531993326096&text=Hello!)
[![Gmail Badge](https://img.shields.io/badge/-Gmail-c14438?style=flat-square&logo=Gmail&logoColor=white&link=mailto:wander.douglas14@gmail.com)](mailto:wander.douglas14@gmail.com)

Feito com muito ❤️☕👨🏻‍💻 por Wander Douglas
