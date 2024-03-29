# My Docker Commands

### Docker Container
Container oluşturur ve çalıştırır
``` 
docker container run --name somex -d -p 8080:8080 nginx
docker container run -d --name wss -p 80:80 httpd
docker container run -d -p 3000:3000 --name server node
docker container run -d -p 27017:27017 --name db -e MONGO_INITDB_ROOT_USERNAME=admin -e MONGO_INITDB_ROOT_PASSWORD=pass mongo
docker container run --publish 5050:5050 --detach --name ubuntu ubuntu
docker container run --publish 60:60 --detach --name ubuntu ubuntu
``` 
Container oluşturur, çalıştırır ve bash e giriş yapar
``` 
docker container run -it --name ws2 nginx bash
``` 
Container çalıştırır
``` 
docker run --name some-mongo -d mongo:latest
docker container run ubuntu
``` 
Containerleri gösterir
``` 
docker container ls
docker container ls -a
``` 
Çalışan containerları gösterir
```
docker ps
```
Container detaylı bilgisini gösterir
```
docker container inspect ng
docker container inspect ubuntu
```
Containeri durdurur
``` 
docker stop container_name
docker container stop ws proxy db
``` 
Containeri durdurduktan sonra siler
``` 
docker rm container_name
docker rm 5c1a
``` 
Container çalışıyorken siler
``` 
docker rm -f container_name
docker rm -f 5c1a
``` 
Container loglarını görüntüleme
``` 
docker container logs db
``` 
docker-compose.yml dosyasıı sayesınde yml dosyasının içerisindeki Container kurar ve ayağa kaldırır.
``` 
docker-compose -f c:/Users/aygar/...../src/main/resources/docker-compose.yml up -d
docker-compose -f c:/src/main/resources/docker-compose.yml up -d
``` 
yml dosyası ile kurulmuş containerleri ve imageleri siler
``` 
docker-compose down --rmi local
docker images --rmi all
``` 
Containerde bash e girer.
``` 
docker-compose exec -it CONTAINER_NAME bash
``` 
### Docker Network
Bir ağ oluşlturur.
``` 
docker network create NETWORK_NAME
docker network create i_net
docker network create -d bridge my-bridge-network
docker network create --driver bridge redmine_network
``` 
Bir containeri bir networke bağlar.
``` 
docker network connect NETWORK_NAME CONTAİNER_NAME
docker network connect bridge ubuntu1 
``` 
Bir containeri bir networke bağlayarak oluşturma yapar.
``` 
docker container run -d --name CONTAINER_NAME --network NETWORK_NAME nginx
docker container run -d --name inginx --network your_net nginx
docker container run -d --name apache --network your_net httpd
``` 
Networkleri gösterir.
``` 
docker network ls
``` 
Network’ün detaylarını gösterir
``` 
docker network inspect my_network
docker network inspect bridge
```
Containeri networkten koparır.
``` 
docker network disconnect NETWORK_NAME CONTAİNER_NAME
docker network disconnect your_net y_ng 
``` 
Bir network siler.
``` 
docker network RM NETWORK_NAME
docker network rm your_net
``` 
### Docker image
Docker içerisinde image leri kontrol eder
``` 
docker image ls
``` 
Docker içerisinde image detaylı gösterir
``` 
docker image inspect nginx
docker image inspect ubuntu
``` 
