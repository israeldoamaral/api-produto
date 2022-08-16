# api-produto

# Variaveis do banco

MONGO_INITDB_ROOT_USERNAME=mongouser
MONGO_INITDB_ROOT_PASSWORD=mongopwd

# Criando o container do banco MongoDb

docker volume create mongo_vol

docker container run -d -e MONGO_INITDB_ROOT_USERNAME=mongouser -e MONGO_INITDB_ROOT_PASSWORD=mongopwd -v mongo_vol:/data/db -p 27017:27017 mongo:4.4.3

# Criar a imagem da aplicação

docker build -t israeldoamaral/api-produto:v1 .

docker push israeldoamaral/api-produto:v1

docker tag israeldoamaral/api-produto:v1 israeldoamaral/api-produto:latest

docker push israeldoamaral/api-produto:latest
