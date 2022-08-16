# api-produto

# Variaveis do banco

MONGO_INITDB_ROOT_USERNAME=mongouser
MONGO_INITDB_ROOT_PASSWORD=mongopwd

# Criar a rede para os containers
docker network create produto_net

# Criar o volume para o banco mongo
docker volume create mongo_vol

# Criando o container do banco MongoDb

docker container run -d -e MONGO_INITDB_ROOT_USERNAME=mongouser -e MONGO_INITDB_ROOT_PASSWORD=mongopwd -v mongo_vol:/data/db -p 27017:27017 --network produto_net --name mongodb mongo:4.4.3

# Criar a imagem da aplicação

docker build -t israeldoamaral/api-produto:v1 .

docker push israeldoamaral/api-produto:v1

docker tag israeldoamaral/api-produto:v1 israeldoamaral/api-produto:latest

docker push israeldoamaral/api-produto:latest
