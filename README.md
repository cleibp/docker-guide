# Docker - Basic command guide

# ![Docker](https://user-images.githubusercontent.com/6461792/109390363-f782e680-78ef-11eb-9e79-a9e47d96e700.png)

Docker é um conjunto de produtos de plataforma como serviço (PaaS) que usam virtualização de nível de sistema operacional para entregar software em pacotes chamados contêineres. Os contêineres são isolados uns dos outros e agrupam seus próprios softwares, bibliotecas e arquivos de configuração. Eles podem se comunicar uns com os outros por meio de canais bem definidos. Todos os contêineres são executados por um único kernel do sistema operacional e, portanto, usam menos recursos do que as máquinas virtuais.


```
                    ##        .            
              ## ## ##       ==            
           ## ## ## ##      ===            
       /""""""""""""""""\___/ ===        
  ~~~ {~~ ~~~~ ~~~ ~~~~ ~~ ~ /  ===- ~~~   
       \______ o          __/            
         \    \        __/             
          \____\______/ 
```

# Comandos docker

Lista de comandos basicos do docker

## Manipulando containers

- `docker ps -a` Lista containers 
```
docker ps -a
```

- `docker ps`  Lista todos os containers em execução
```
docker ps
```

- `docker inspect <NOME ou ID>` inpeciona um container
```
docker inspect <NOME ou ID>
```

- `docker stop <NOME ou ID>`  para um container
```
docker stop <NOME ou ID>
```

- `docker restart <NOME ou ID>`  reinicia um container
```
docker restart <NOME ou ID>
```

- `docker start <NOME ou ID>`  inicia um container
```
docker start <NOME ou ID>
```

- `docker rm <NOME ou ID>`  remove um container
```
docker rm <NOME ou ID>
```

- `docker stats <NOME ou ID>`  verifica quanto recurso o container está consumido
```
docker stats <NOME ou ID>
```

- `docker top <NOME ou ID>`  verifica os processos que estão sendo executados no container
```
docker top <NOME ou ID>
```

- `docker logs <NOME ou ID>`  visualiza os logs do container
```
docker logs <NOME ou ID>
```

- `docker run -d <IMAGEM>`  executa o container em segundo plano
```
docker run -d <IMAGEM>
```

- `docker run -p <PORTA_HOST>:<PORTA_CONTAINER> <IMAGEM>`  executa o container em segundo plano: Exemplo: docker run  -d -p 8080:80 nginx
```
docker run  -d -p 8080:80 nginx
```

- `docker run --name <NOME_DA_IMAGEM> <IMAGEM>`  nome para seu container
```
docker run --name <NOME_DA_IMAGEM> <IMAGEM>
```


- `docker container prune`  remove todos os containers que estão parados
```
docker container prune
```

- `docker run --name <NOME_DA_IMAGEM> --link <CONTAINER> -d -p PORTA_HOST>:<PORTA_CONTAINER> <IMAGEM>`  linkando container. Exemplo: docker run --name blog_wordpress --link dbserver:mysql -d -p 8090:80 wordpress
```
docker run --name blog_wordpress --link dbserver:mysql -d -p 8090:80 wordpress
```



## Manipulando imagens

- `docker images`  Lista as imagens
```
docker images
```

- `docker rmi <NOME ou ID>`  remove uma imagem
```
docker rmi <NOME ou ID>
```

- `docker commit <NOME ou ID> <NOME_DA_IMAGEM>`  gera uma imagem a partir de um container. Exemplo: docker commit b0ccb8cc6854 ngnix_default:v1
```
docker commit <NOME ou ID> <NOME_DA_IMAGEM>
```

## Executar comandos dentro do container

- `docker exec <NOME ou ID> ls` lista pastas
```
docker exec <NOME ou ID> ls
```

- `docker exec -it <NOME ou ID> /bin/bash` acessa terminal do container
```
docker exec -it
```


## Volumes

- `docker volume ls` lista todos os volumes
```
docker volume ls
```

- `docker volume rm <NOME VOLUME>` remove um ou mais volumes
```
docker volume rm
```

- `docker volume inspect <NOME VOLUME>` exibe informações volume
```
docker volume inspect
```

- `docker volume create <NOME VOLUME>` cria um volume
```
docker volume create
```

- `docker volume prune ` remove todos os volumes não usados
```
docker volume prune
```

- `docker run -d -it -v /<PASTA>  <NOME ou ID IMAGEM>` cria um volume. Exemplo: docker run -d -it -v /data --name web04 nginx
```
docker run -d -it -v /data --name web04 nginx
```

- `docker run -d -p <PORTA_HOST>:<PORTA_CONTAINER> --name <NOME> -v /C/dev/:/usr/share/ngnix/html <IMAGEM>` compartilha volume. Exemplo: docker run -d -p 8087:80 --name web07 -v /c/dev/:/usr/share/nginx/html nginx
```
docker run -d -p 8087:80 --name web07 -v /c/dev/:/usr/share/nginx/html nginx
```

- `docker run -d -p <PORTA_HOST>:<PORTA_CONTAINER> --volumes-from <NOME ou ID> --name <NOME PARA O CONTAINER> <IMAGEM>` compartilha volume com container. Exemplo: docker run -d -p 8088:80 --volumes-from web07 --name web08 nginx
```
docker run -d -p 8088:80 --volumes-from web07 --name web08 nginx
```


## Redes

- `docker network ls` lista todos as redes
```
docker network ls
```

- `docker network create --driver <DRIVER> <NOME>` cria uma rede. Exemplo: docker network create --driver bridge alpine-net
```
docker network create --driver bridge alpine-net
```

- `docker run -d --name <NOME_DA_IMAGEM> --network <NOME DA REDE> <IMAGEM>`  atribuindo um container a uma rede. Exemplo: docker run -d --name ngnix03 --network alpine-net nginx:alpine
```
docker run -d --name ngnix03 --network alpine-net nginx:alpine
```

- `docker network inspect <NOME/ID REDE> ` exibe informações de uma rede
```
docker network inspect
```

- `docker network prune` remove todas as redes não usadas
```
docker network prune
```

- `docker network rm <NOME/ID REDE>` remove uma ou mais redes
```
docker network rm
```


## Contatos

[![Github Badge](https://img.shields.io/badge/-Github-000?style=flat-square&logo=Github&logoColor=white&link=https://github.com/cleibp)](https://github.com/cleibp)
[![Linkedin Badge](https://img.shields.io/badge/-LinkedIn-blue?style=flat-square&logo=Linkedin&logoColor=white&link=https://www.linkedin.com/in/cleitonpaiva/)](https://www.linkedin.com/in/cleitonpaiva/)
[![Whatsapp Badge](https://img.shields.io/badge/-Whatsapp-4CA143?style=flat-square&labelColor=4CA143&logo=whatsapp&logoColor=white&link=https://api.whatsapp.com/send?phone=5516988368457&text=Ola!)](https://api.whatsapp.com/send?phone=5516988368457&text=Ola!)
[![Gmail Badge](https://img.shields.io/badge/-Gmail-c14438?style=flat-square&logo=Gmail&logoColor=white&link=mailto:cleibp@gmail.com)](mailto:cleibp@gmail.com)

Feito com muito ❤️☕👨🏻‍💻 por Cleiton Paiva

