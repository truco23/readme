# Comandos Docker

__sintaxe__ => docker <comando> <subcomando> <opções>

__docker --help__ => mostra os comandos docker disponíveis 

__docker container ls__ => lista os containers em execução

__docker container ls -a__ => lista todos os containers inclusive os parados

__docker container ls -a -q__ => lista os todos os ids dos containers

__docker container rm id/name__ => remove um container pelo id ou nome

__docker container run -p porta:porta nome_imagem -d__ => inicia um container docker em segundo plano -d

__docker container run -d -P nome_imagem__ => inicia um container em segundo plano com a porta aleatória -P

__docker container run -d -P --name nome_sua_escolha nome_imagem__ => inicia um container em segundo plano com a porta aleatória -P && define um nome do container --name

__docker container logs nome_imagem__ => exibe os logs do container

__docker container logs -f nome_imagem__ => exibe os logs do container com console travado

__docker container top nome_image__ => lista os processos do container

__docker container stats__ => exibe o consumo de todos os container em execução

__docker container stats nome_image__ => exibe o consumo de um container em execução

### Criar imagem do MongoDB
docker run --name mongodb -p 27017:27017 -e MONGO_INITDB_ROOT_USERNAME=admin -e MONGO_INIT_ROOT_PASSWORD=admin -d mongo

### Criar imagem MongoClient

docker run --name mongoclient -p 3333:3333 --link mongo:mongo -d mongoclient/mongoclient