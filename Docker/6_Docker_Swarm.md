## Swarm
#### Swarm çalıştırma:
``` 
docker swarm init
``` 
#### service listemele:
``` 
docker service ls
``` 
#### Service kurma:
``` 
docker service create alphine
``` 
#### Service yi silme :
``` 
docker service rm ID
docker service rm agsp33 ncy1gg
``` 
#### Node leri listeler
``` 
docker service ps SERVICE_ID
docker service ps xx22i
``` 
#### Service de replica oluşturma
``` 
docker service update loving_engelbart --replicas 4
``` 
