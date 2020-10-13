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
docker containner run ubuntu
``` 
Containerleri gösterir
``` 
docker container ls
docker container ls -a
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
Container loglarına bakar
``` 
docker container logs db
``` 
docker-compose.yml dosyasıı sayesınde yml dosyasının içerisindeki Container kurar ve ayağa kaldırır.
``` 
docker-compose -f c:/src/main/resources/docker-compose.yml up -d
``` 
yml dosyası ile kurulmuş containerleri ve imageleri silmek isterseniz eğer
``` 
docker-compose down --rmi local
docker images --rmi all
``` 
