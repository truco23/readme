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