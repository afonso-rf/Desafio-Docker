# Questão 05

Chegou um cliente pra você que possui todas as suas aplicações em data centers e a
gestão dessas aplicações está cada vez mais complexa então pra iniciar um plano de
gestão unificada e migração pra um ambiente cloud, as aplicações serão migradas pra
containers. E hoje você precisa iniciar esse processo com um projeto piloto, o portal de
conteúdos da empresa construido em Wordpress. Então hoje sua missão é criar esse
ambiente wordpress pronto para a equipe de publicidade começar a popular.


## - Resposta

 Criei o arquivo [docker-compose.yaml](wordpress/docker-compose.yaml) para subir todo o ambiente necessario.

### Variaveis de Ambientes utilizadas no manifesto

IMAGE_WP_TAG => Variavel de ambiente para a tag da imagem do Wordpress (Em caso não tenha a variavel, será usada a versão "latest"). 

IMAGE_DB_TAG => Variavel de ambiente para a tag da imagem do MariaDB (Em caso não tenha a variavel, será usada a versão "latest").

DB_ROOT_PASSWORD => Variavel de ambiente para a senha ROOT do MariaDB Em caso não tenha a variavel, será usado (Em caso não tenha a variavel, será usado "rootpwd").

DB_USERNAME => Variavel de ambiente para o usurario do MariaDB (Em caso não tenha a variavel, será usado "mariadbuser").

DB_PASSWORD => Variavel de ambiente para a senha de usuario do MariaDB (Em caso não tenha a variavel, será usado "mariadbpwd").

DB_DATABASE => Variavel de ambiente para a senha de usuario do MariaDB (Em caso não tenha a variavel, será usado "wordpress"). 
