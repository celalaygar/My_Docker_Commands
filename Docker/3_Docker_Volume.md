##  Volume
#### Volume oluşturma:
``` 
docker volume create volume_ismi
Örnek: docker volume create ilkvolume 
``` 
#### Volume ile ilgili detayları inceleme:
``` 
docker volume inspect volume_id|ya da|volume_ismi
Örnek: docker volume inspect ilkvolume
``` 
#### Sistemdeki tüm volumeleri listeleme:
``` 
docker volume ls
``` 
#### Volume’u container’a bağlama (-v):
``` 
docker container run -v volume_ismi:container_icindeki_path image:tag
Örnek: docker container run -v ilkvolume:/var/www/html image:tag
``` 
#### Volume’u container’a sadece okunur şekilde bağlama (:ro):
``` 
docker container run -v volume_ismi:container_icindeki_path:ro image:tag
Örnek: docker container run -v ilkvolume:/var/www/html:ro image:tag
``` 
#### Host üstündeki bir klasör ya da dosyayı bind mount olarak bağlama:
``` 
docker container run -v host_klasör_path:container_icindeki_path image:tag
docker container run -v c:\websitesi:/usr/share/nginx/html nginx:latest 
``` 
#### Volume silme:
``` 
docker volume rm volume_ismi
Örnek: docker volume rm ilkvolume
``` 
