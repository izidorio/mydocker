instalar o docker io
```
sudo apt-get update && apt-get upgrade -y
sudo apt-get install docker.io -y
sudo apt-get install docker-compose -y
```
- dar permissão ao usuário para executar o docker
```
sudo groupadd docker
sudo usermod -aG docker ${USER}
docker info
```
- caso resulte em erro executar com o usuário root
```
# crie uma senha para o usuário root caso não exista
sudo passwd root

su root
usermod -aG docker ${USER}

su ubuntu
docker info
```

clonar o projeto
```
cd /var/www
git clone https://github.com/izidorio/mydocker.git docker
```

criar o .env
```
cd /var/www/docker
cp .env-example .env
```

principais variáveis
```
nano .env

DATA_PATH_HOST=~/storage/data
POSTGRES_DB=default
POSTGRES_USER=default
POSTGRES_PASSWORD=secret
PGADMIN_DEFAULT_EMAIL=pgadmin4@pgadmin.org
PGADMIN_DEFAULT_PASSWORD=admin
```

clone seu projeto no mesmo diretório do docker
```
/var/www
        | docker
        | projeto 
```

executar o docker-compose
```
cd /var/www/docker
docker-compose up -d
```

executar o workspace
```
cd /var/www/docker
docker-compose exec workspace bash
```



