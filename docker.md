# Comandos Docker

### Sintaxe e ajuda
__docker <comando> <subcomando> <opções>__ => sintaxe comandos docker

__docker --help__ => mostra os comandos docker disponíveis 

### Listagem

__docker container ls__ => lista os containers em execução

__docker container ls -a__ => lista todos os containers inclusive os parados

__docker container ls -a -q__ => lista os todos os ids dos containers

__docker image ls__ => lista as imagens que já foram baixadas

### Logs

__docker container logs nome_imagem__ => exibe os logs do container

__docker container logs -f nome_imagem__ => exibe os logs do container com console travado

### Serviços

__docker container top nome_image__ => lista os processos do container

### Consumo

__docker container stats__ => exibe o consumo de todos os container em execução

__docker container stats nome_image__ => exibe o consumo de um container em execução

### Remoção

__docker container rm id/name__ => remove um container pelo id ou nome

__docker image rm id/name__ => remove uma imagem pelo id ou nome

### Iniciar containers

__docker container run -p porta:porta nome_imagem -d__ => inicia um container docker em segundo plano -d

__docker container run -d -P nome_imagem__ => inicia um container em segundo plano com a porta aleatória -P

__docker container run -d -P --name nome_sua_escolha nome_imagem__ => inicia um container em segundo plano com a porta aleatória -P && define um nome do container --name

__docker container run --name mongodb -d -p 27017:27017 mongo:4__ => criar container do MongoDB

__docker container run --name mongodb -d -p 27017:27017 -e MONGO_INITDB_ROOT_USERNAME=admin -e MONGO_INIT_ROOT_PASSWORD=admin mongo:4__ => criar container do MongoDB com usuário e senha

__docker container run --name mongoclient -d -p 3333:3000 --link mongodb:mongodb mongoclient/mongoclient__ => cria container do mongoclient

### Executar containers

__docker container exec -it mongodb mongo admin__ => linha de comando para iniciar terminal MongoDB com apelido __mongodb__ e a imagem __mongo__ senha __admin__