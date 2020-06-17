# CLI mongo


### Listagem

__show dbs__ => lista as databases cadastradas

__show collections__ => lista as coleções cadastradas


### Criar/Alterar database

__use nome_database__ => cria/altera para uma database


### Inserção

__db.nome_collection.insert({})__ => cria uma nova collection


### Listagem

__db.nome_collection.find()__ => lista todos os dados da collection

__db.nome_collection.find().pretty()__ => lista todos os dados da collection com formatação

__db.nome_collection.find({nome: 'teste'})__ => lista um dado específico na collection


### Atualização

__db.nome_collection.update({id: '123'}, {$set: {nome: 'novo nome'}})__ => altera somente os valores no objeto $set


### Remoção

__db.nome_collection.remove({})__ => remove todos os dados da collection

__db.nome_collection.remove({id: '123'})__ => remove somente o dado com id 123


### Conexão com o mongoose

__Mongoose.connect('mongodb://nome_usuario:senha_usuario@localhost:27017/nome_database', { useNewUrlParser: true }, (error) => if(!error) return; console.log('falha na conexão') )__ => cria conexão com o mongo

__Mongoose.connection.once('open', () => console.log('database rodando'))__ => verifica se a conexão foi estabelecida

__Mongoose.connection.readyState__ => retorna o estado da conexão
    - 0 disconectado
    - 1 conectado
    - 2 conectando
    - 3 disconectando