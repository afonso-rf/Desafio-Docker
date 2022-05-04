# Questão 06

Agora vamos aumentar mais a complexidade das coisas, chegou a hora de executar
uma aplicação baseada em arquitetura de microsserviços.
Essa aplicação é formada por 3 repositórios:


[Aplicação Web](https://github.com/KubeDev/rotten-potatoes-ms)

[Microsserviço de Filmes](https://github.com/KubeDev/movie)

[Microsserviço de Avaliação](https://github.com/KubeDev/review)

Montar o ambiente com Docker compose baseado em arquivos de enviroment

## - Resposta

Criado o arquivo [docker-compose.yaml](docker-compose.yaml) para rodar a aplicação.

No manifesto, foi declarado 3 networks (1 para o fronend e 2 para o backend), 2 Volumes (1 volume para cada Database) para persistir os dados e nomeado os containers para melhor identificação. 

### Variaveis de Ambientes utilizadas no manifesto

- rotten-potatoes-ms

IMAGE_ROTTEN => Variavel de ambiente para o nome da imagem (Em caso não tenha a variavel, será usado "rotten-potatoes-ms").

ROTTEN_TAG => Variavel de ambiente para a tag da imagem (Em caso não tenha a variavel, será usada a versão "latest"). 


- movie

IMAGE_MOVIE_ROTTEN => Variavel de ambiente para o nome da imagem (Em caso não tenha a variavel, será usado "movie-rotten")

MOVIE_TAG => Variavel de ambiente para a tag da imagem (Em caso não tenha a variavel, será usada a versão "latest"). 

MONGO_TAG => Variavel de ambiente para a tag da imagem do MongoDB (Em caso não tenha a variavel, será usada a versão "4.4.12").

MONGO_DB_USERNAME => Variavel de ambiente para o usurario do MongoDB (Em caso não tenha a variavel, será usado "mongo").

MONGO_DB_PASSWORD => Variavel de ambiente para a senha do usurario do MongoDB (Em caso não tenha a variavel, será usado "mongo").

- Review

IMAGE_REVIEW_ROTTEN => Variavel de ambiente para o nome da imagem (Em caso não tenha a variavel, será usado "review-rotten").

REVIEW_TAG => Variavel de ambiente para a tag da imagem (Em caso não tenha a variavel, será usada a versão "latest").

POSTGRES_TAG => Variavel de ambiente para a tag da imagem do PostgresSQL (Em caso não tenha a variavel, será usada a versão "latest").

POSTGRES_DB_USERNAME => Variavel de ambiente para o usurario do PostgresSQL (Em caso não tenha a variavel, será usado "postgres").

POSTGRES_DB_PASSWORD => Variavel de ambiente para a senha do usurario do PostgresSQL (Em caso não tenha a variavel, será usado "postgres").
