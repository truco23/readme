# docker-compose.yml

version: "3.1"
services:
  mongoservice: 
    image: mongo
    container_name: mongodb
    command: --serviceExecutor adaptive
    environment:
      MONGO_INITDB_ROOT_USERNAME: teste
      MONGO_INITDB_ROOT_PASSWORD: teste
      MONGO_INITDB_DATABASE: database_teste
    ports:
      - "27017:27017"
  mongoclientservice:
    image: mongoclient/mongoclient
    container_name: mongoclient
    ports:
      - "3001:3000"
    links:
      - mongoservice
    depends_on:
      - mongoservice