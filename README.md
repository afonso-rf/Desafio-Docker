![image](img/kubdev.png)

# KubeDev - Desafio de Docker


Um dos primeiros ganhos que temos com o uso do Docker é em ambiente de
desenvolvimento. Criar um ambiente com banco de dados, mensageria é tão simples
quanto executar alguns comandos. Então agora tá na hora de você genhar com isso
também

#

## Questão 01


Execute os comandos para criar os 4 bancos de dados listados com containers, e use
como se tivesse instalado eles localmente na sua máquina (Não esquece de garantir
que não vai perder os dados caso o container seja excluido).

MongoDB

MariaDB

PostgreSQL

Redis

#

## Questão 02

Certo, você conseguiu criar 4 bancos na sua máquina utilizando containers. Mas tem
uma coisa, não adianta só conectar a aplicação no banco quando se está
desenvolvendo, é preciso também acessar o banco, executar comandos e consultar a
base. Então vamos fazer isso da forma KubeDev de ser, com containers !!! Cada banco
de dados tem uma ferramenta administrativa com interface web que você pode usar.

    MongoDB ⇒ Mongo Express

    MariaDB ⇒ phpmyadmin

    PostgreSQL ⇒ PgAdmin

    Redis ⇒ redis-commander

#

## Questão 03

Um dos fundamentos chave pra se trabalhar com container é a criação de imagens
Docker. E criar uma imagem Docker pra cada aplicação sempre muda dependendo de 
como ela foi desenvolvida. 

Um cliente entrou em contato e expos o principal problema para a migração pra 
ambiente baseado em containers.

Então agora eu tenho aqui algumas aplicações que precisam ser executadas em
containers mas eu só tenho o código fonte delas, chegou a hora de você mostrar seu
talento e executar essas aplicações em containers Docker e deixar acessível na sua
máquina local.(Pesquise e entenda como cada plataforma é utilizada antes de começar
a criar a imagem)

[Aplicação escrita em NodeJS](https://github.com/KubeDev/conversao-temperatura)

[Aplicação escrita em Python utilizando Flask](https://github.com/KubeDev/conversao-distancia)

[Aplicação escrita em C# utilizando ASP.NET Core](https://github.com/KubeDev/conversao-peso)

Faça um fork de cada projeto para o seu GitHub e depois me envia aqui embaixo cada
um deles com a solução. (Não esquece de documentar no Readme).

# 

## Questão 04

Agora que você já afiou o seu conhecimento sobre criação de imagens Docker, tá na
hora de fazer o deploy de uma aplicação 100% em containers Docker. A aplicação está
no [GitHub do KubeDev](https://github.com/KubeDev/rotten-potatoes) e um detalhe MUITO importante, a aplicação precisa ser toda
criada com apenas uma linha de comando.

#

## Questão 05

Chegou um cliente pra você que possui todas as suas aplicações em data centers e a
gestão dessas aplicações está cada vez mais complexa então pra iniciar um plano de
gestão unificada e migração pra um ambiente cloud, as aplicações serão migradas pra
containers. E hoje você precisa iniciar esse processo com um projeto piloto, o portal de
conteúdos da empresa construido em Wordpress. Então hoje sua missão é criar esse
ambiente wordpress pronto para a equipe de publicidade começar a popular.

#

## Questão 06

Agora vamos aumentar mais a complexidade das coisas, chegou a hora de executar
uma aplicação baseada em arquitetura de microsserviços.
Essa aplicação é formada por 3 repositórios:


[Aplicação Web](https://github.com/KubeDev/rotten-potatoes-ms)

[Microsserviço de Filmes](https://github.com/KubeDev/movie)

[Microsserviço de Avaliação](https://github.com/KubeDev/review)

Montar o ambiente com Docker compose baseado em arquivos de enviroment

#

## Questão 07

Agora que você concluiu, tão importante quanto executar, é documentar. Então crie
anotações sobre cada questão, detalhe as tomadas de decisão e processo de
construção.

E pra ficar melhor ainda, crie posts no Linkedin sobre o processo e não se esquece de
me marcar e colocar a nossa #rumoaelite !!!!
