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

### mongo com mongo-express

version: '3'
services:
  mongo:
    image: mongo
    container_name: mongodb
    environment:
      MONGO_INITDB_ROOT_USERNAME: root
      MONGO_INITDB_ROOT_PASSWORD: MongoAdmin
    ports:
      - "27017:27017"
    networks:
      - mongo-compose-network

  mongo-express:
    image: mongo-express
    container_name: mongo-express
    ports:
      - 8080:8081
    environment:
      ME_CONFIG_BASICAUTH_USERNAME: user
      ME_CONFIG_BASICAUTH_PASSWORD: user
      ME_CONFIG_MONGODB_PORT: 27017
      ME_CONFIG_MONGODB_ADMINUSERNAME: root
      ME_CONFIG_MONGODB_ADMINPASSWORD: MongoAdmin
    links:
      - mongo
    depends_on:
      - mongo
    networks:
      - mongo-compose-network

networks: 
    mongo-compose-network:
      driver: bridge