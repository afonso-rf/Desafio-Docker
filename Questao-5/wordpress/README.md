# Desafio-KubeDev - Docker: Q5

Criado um .yaml para rodar com o docker-compose. 

#

IMAGE_WP_TAG => Variavel de ambiente para a tag da imagem do Wordpress.

IMAGE_DB_TAG => Variavel de ambiente para a tag da imagem do MariaDB.

DB_ROOT_PASSWORD => Variavel de ambiente para a senha ROOT do MariaDB.

DB_USERNAME => Variavel de ambiente para o usurario do MariaDB.

DB_PASSWORD => Variavel de ambiente para a senha de usuario do MariaDB.

#

## MariaDB


### Configuração

MYSQL_ROOT_PASSWORD: => Para a senha ROOT do MariaDB

MYSQL_USER => Usuario para acesso ao MariaDB

MYSQL_PASSWORD => Senha do usuario para acesso ao MariaDB

MYSQL_DATABASE => Nome do DB no MariaDB

#

## Wordpress


### Configuração

WORDPRESS_DB_HOST => Caminho para acesso ao DB

WORDPRESS_DB_USER => Usuario para acessar o DB

WORDPRESS_DB_PASSWORD => Senha de usuario para acessar o DB

WORDPRESS_DB_NAME => Nome do DB
