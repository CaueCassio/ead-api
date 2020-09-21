# ead-api

API RESTFul da plataforma de ensino a distância. Projeto em Node/JS seguindo boas práticas e de fácil integração.

# Dependências
Node 14.3 e NPM (apenas se desejar rodar fora do container)
Docker
Docker Compose
Configurando e rodando local
Renomeie o arquivo .env.example para .env, gere uma SECRET_KEY e adicione o valor a variável SECRET_KEY no arquivo. Para rodar local, você pode por qualquer valor no SECRET_KEY ou gerar uma de forma mais segura com o comando:

node -e "console.log(require('crypto').randomBytes(256).toString('base64'));"
Rode os containers
docker-compose up -d
Configure o MongoDB
Para rodar o projeto local, é necessário criar o usuário do banco de dados eadapi que utilizamos no sistema. Acesse o container docker do mongo pelo terminal:

docker exec -it eadapi-mongo /bin/bash

# Axecute o seguinte comando dentro do container:

mongo -uroot -pexample <<EOF
  use eadapi
  db.createUser({
    user: "ead_api_user",
    pwd: "ead_api_user",
    roles: ["readWrite"]
  })
EOF
Acessando logs
Para visualizar os logs, é necessário rodar o comando do docker para visualizar os logs do container.

docker logs -f eadapi-api
# Tecnologias
Node
HapiJS Framework
MongoDB
Redis
MySQL

