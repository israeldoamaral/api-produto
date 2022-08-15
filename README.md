# api-produto

# Variaveis do banco

MONGO_INITDB_ROOT_USERNAME=mongouser
MONGO_INITDB_ROOT_PASSWORD=mongopwd

# Criando o container do banco MongoDb

docker container run -d -e MONGO_INITDB_ROOT_USERNAME=mongouser -e MONGO_INITDB_ROOT_PASSWORD=mongopwd -p 27017:27017 mongo:4.4.3
