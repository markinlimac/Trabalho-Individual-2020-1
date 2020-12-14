# Solução do Trabalho
[![Maintainability](https://api.codeclimate.com/v1/badges/d1bf681ba115136607ea/maintainability)](https://codeclimate.com/github/markinlimac/Trabalho-Individual-2020-1/maintainability)
[![Test Coverage](https://api.codeclimate.com/v1/badges/d1bf681ba115136607ea/test_coverage)](https://codeclimate.com/github/markinlimac/Trabalho-Individual-2020-1/test_coverage)

## Containerização
Para fazer a containerização foi utilizado o docker e para fazer a orquestração foi utilizado o docker-compose.

Para executar o projeto basta executar os seguintes comandos:
```
sudo docker-compose build
sudo docker-compose run api rake db:create 
sudo docker-compose run api rake db:migrate 
sudo docker-compose up
```
O docker-compose ira fazer a orquestração e subir o front-end na porta 8080 e o back-end na porta 3000.

## Pipeline
Para fazer o CI, foi utilizado o Github Actions. Foi criado 2 pipelines, uma para o front e outra para o back.

O nome da pipeline do back é `api`  
O nome da pipeline do front é `client`  

O CI executa as seguintes etapas:
- API:
  - Runner download
  - Set up Ruby
  - Install dependencies
  - Run database
  - Execute tests on api

- CLIENT:
  - Runner download
  - Set up Node
  - Install dependencies
  - Execute tests on client
  - Client coverage

O coverage esta pegando apenas o front-end.
