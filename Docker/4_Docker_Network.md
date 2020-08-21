## Network
#### Kullanıcı tanımlı bridge network oluşturma (bridge):
``` 
docker network create --driver=bridge network_ismi
Örnek: docker network create --driver=bridge kopru
``` 
#### Kullanıcı tanımlı bridge network oluşturma (ip bilgilerini belirleyerek):
``` 
docker network create --driver=bridge --subnet=cidr --ip-range=cdir --gateway=ip_adresi network_ismi
Örnek: docker network create --driver=bridge --subnet=10.10.0.0/16 --ip-range=10.10.10.0/24 --gateway=10.10.10.10 kopru
``` 
#### Sistemdeki tüm volumeleri listeleme:
``` 
docker network ls
``` 
#### Volume ile ilgili detayları inceleme:
``` 
docker network inspect network_ismi
Örnek: docker network inspect kopru
``` 
#### Container’ı varsayılan dışında bir network’e bağlayarak çalıştırma:
``` 
docker container run --network network_ismi image:tag
Örnek: docker container run --network kopru nginx:latest
``` 
#### Çalışan bir container’ı başka bir network’e bağlama:
``` 
docker network connect network_ismi container_id|ya da|container_ismi
Örnek: docker network connect kopru 12a793b3fec0
``` 
#### Çalışan bir container’ın bağlı olduğu networkle bağlantısını kesme:
``` 
docker network disconnect network_ismi container_id|ya da|container_ismi
Örnek: docker network disconnect kopru 12a793b3fec0
``` 
#### Port publish ederek bir container çalıştırma (-p):
``` 
docker container run -p host_portu:container_portu/tcp_yada_udp image:tag
Örnek: docker container run -p 8080:80 -p 53:53/udp nginx:latest
``` 
