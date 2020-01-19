# My_Docker_Commands


### Docker Container
container oluşturur ve çalıştırır
``` 
docker container run --name somex -d -p 8080:8080 nginx
docker container run -d --name wss -p 80:80 httpd
docker container run -d -p 3000:3000 --name server node
docker container run -d -p 27017:27017 --name db -e MONGO_INITDB_ROOT_USERNAME=admin -e MONGO_INITDB_ROOT_PASSWORD=pass mongo
docker container run --publish 5050:5050 --detach --name ubuntu ubuntu
docker container run --publish 60:60 --detach --name ubuntu ubuntu

``` 
container oluşturur, çalıştırır ve bash e giriş yapar
``` 
docker container run -it --name ws2 nginx bash
``` 
container çalıştırır
``` 
docker run --name some-mongo -d mongo:latest
docker containner run ubuntu
``` 
containerleri gösterir
``` 
docker container ls
docker container ls -a
``` 
containeri durdurur
``` 
docker stop container
docker container stop ws proxy db
``` 
containeri durdurduktan sonra siler
``` 
docker rm 5c1a
``` 
container loglarına bakar
``` 
docker container logs db
``` 
docker-compose.yml dosyasıı sayesınde container kurar
``` 
docker-compose -f c:/Users/aygar/workspace-spring-tool-suite-4/maven-example/spring-mongo/src/main/resources/docker-compose.yml up -d
``` 

### Docker Network
``` 
docker network connect NETWORK_NAME CONTAİNER_NAME
``` 

networkleri gösterir
``` 
docker network ls
``` 
