# Questão 01 -

Execute os comandos para criar os 4 bancos de dados listados com containers, e usecomo se tivesse instalado eles localmente na sua máquina (Não esquece de garantirque não vai perder os dados caso o container seja excluido).

#### Como criar um banco MongoDB *

	docker container run -d --name mongo_db -p '27017:27017' --volume 'mongo_db_vol:/data/db' -e MONGO_INITDB_ROOT_USERNAME='mongouser' -e MONGO_INITDB_ROOT_PASSWORD='mongopwd' mongo:4.4.12

#### Como criar um banco MariaDB *

	docker container run -d --name maria_db -p '3306:3306' --volume 'maria_db_vol:/var/lib/mysql'  -e MYSQL_ROOT_PASSWORD='rootpwd' -e MYSQL_USER='mariauser' -e MYSQL_PASSWORD='mariapwd'  mariadb:10.7.1

### Como criar um banco PostgreSQL *

	docker container run -d --name postgres_db -p '5432:5432'  --volume 'postgres_db_vol:/var/lib/postgresql/data' -e POSTGRES_PASSWORD='rootpwd'   postgres:14-alpine3.15

#### Como criar um banco Redis *

	docker container run -d --name redis_db -p '6379:6379' --volume 'redis_db_vol:/data' redis:7.0-rc-alpine3.15

#

# Questão 02 - 

Certo, você conseguiu criar 4 bancos na sua máquina utilizando containers. Mas temuma coisa, não adianta só conectar a aplicação no banco quando se estádesenvolvendo, é preciso também acessar o banco, executar comandos e consultar abase. Então vamos fazer isso da forma KubeDev de ser, com containers !!! Cada bancode dados tem uma ferramenta administrativa com interface web que você pode usar.

####  MongoDB ⇒ Mongo Express (https://github.com/mongo-express/mongo-express) *

	docker network create mongo_net

	docker network connect mongo_net mongo_db

	docker container run -d --name mongo-express -p '8081:8081' --network 'mongo_net' -e ME_CONFIG_MONGODB_ADMINUSERNAME='mongouser' -e ME_CONFIG_MONGODB_ADMINPASSWORD='mongopwd' -e ME_CONFIG_MONGODB_SERVER='mongo_db' mongo-express:1.0.0-alpha

	Acessível pelo http://localhost:8081/ 

	Sem precisar de user/senha. Acesso OK.


#### MariaDB ⇒ phpmyadmin (https://www.phpmyadmin.net) *

	docker network create maria_net

	docker network connect maria_net

	docker container run -d --name phpmyadmin -p '8080:80' --network 'maria_net' -e MYSQL_ROOT_PASSWORD='rootpwd' -e PMA_HOST='maria_db'  phpmyadmin:5.1.3-apache

	Acessível pelo http://localhost:8080/ 

	Precisa de username/senha. root:rootpwd ou o user criado mariauser:mariapwd. Acesso OK.

#### PostgreSQL ⇒ PgAdmin (https://www.pgadmin.org) *
	
	docker network create postgres_net
	
	docker network connect postgres_net postgres_db
	
	docker container run -d --name pgadmin4 -p 8082:80 --network 'postgres_net' -e PGADMIN_DEFAULT_EMAIL='admin@admin.com' -e PGADMIN_DEFAULT_PASSWORD='adminpwd' dpage/pgadmin4:5.5

	Acessível pelo http://localhost:8082/ 
	
	Precisa username/senha. admin@admin.com:adminpwd. 
	Necessário cadastro do Banco PostgreSQL : Add New Server > General/Name:postgres_db |  Connection/Host name:postgres_db, Username:postgres, Password:rootpwd | Save. Acesso OK.

#### Redis ⇒ redis-commander (https://hub.docker.com/r/rediscommander/redis-commander) *
	
	docker network create redis_net
	
	docker network connect redis_net redis_db
	
	docker container run -d --name redis-cmd --network 'redis_net' -p '8083:8081' rediscommander/redis-commander:latest

	Acessível pelo http://localhost:8083/ 
	
	Sem precisar de user/senha. Necessario o cadastro do Banco Redis: More > Add Server/Display-Name:redis_db, Hostname:redis_db, Connect. Acesso OK.
	
	
