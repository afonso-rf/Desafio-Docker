# Questão 04

Agora que você já afiou o seu conhecimento sobre criação de imagens Docker, tá na
hora de fazer o deploy de uma aplicação 100% em containers Docker. A aplicação está
no [GitHub do KubeDev](https://github.com/KubeDev/rotten-potatoes) e um detalhe MUITO importante, a aplicação precisa ser toda
criada com apenas uma linha de comando.

## Resposta

Para criar somente em um comando, criei o arquivo [docker-compose.ymal](rotten-potatoes/docker-compose.yaml).


### Variaveis de Ambientes utilizadas no manifesto 


 - Para o MongoDB 

MONGO_TAG = > Versão do Mongo DB (Em caso não tenha a variavel, será usada a versão "4.4.12")

MONGO_USERNAME => User do Mongo DB (Em caso não tenha a variavel, será usado "mongouser")

MONGO_PASSWORD => Seha do user do Mongo DB (Em caso não tenha a variavel, será usado "mongopwd")


 - Para a API rotten-potatoes

IMAGE_API => Nome imagem a ser criada/utilizada. (Em caso não tenha a variavel, será usado o nome "rotten-potetoes)

IMAGE_API_TAG => Versão da imagem a ser criada/utilizada. (Em caso não tenha a variavel, será usada a versão latest)
