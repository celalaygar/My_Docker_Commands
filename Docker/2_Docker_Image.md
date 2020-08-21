## Image
#### Docker CLI aracılığıyla registery’de oturum açma:
``` 
docker login registery_url
Örnek: docker login localhost:8080
``` 
#### Sisteme bir imaj çekme:
``` 
docker image pull image:tag
Örnek: docker image pull nginx:latest
``` 
#### Docker hub’a (ya da başka bir repository) image gönderme:
``` 
docker image push repository/image:tag
Örnek: docker image push ozgurozturknet/adanzyedocker:latest
``` 
#### Mevcut bir imaja yeni tag ekleme
``` 
docker image tag image:tag yeniimage:tag
Örnek: docker image tag nginx:latest ozgurozturknet\nginx:v1
``` 
#### Image ile ilgili detayları inceleme:
``` 
docker image inspect image:tag
Örnek: docker image inspect nginx:latest
``` 
#### Image layerlarını listeleme:
``` 
docker image history image:tag
Örnek: docker image history nginx:latest
``` 
#### Dockerfile kullanarak yeni bir imaj yaratma:
``` 
docker image build -t image:tag .
Örnek: docker image build -t ozgurozturknet\merhaba-dunya:latest . (Dockerfile dosyası komutun çalıştırıldığı folder’da bulunmalı)
``` 
#### Image oluştururken build arg kullanma:
``` 
docker image build --build-arg arg=deger -t image:tag .
Örnek: docker image build --build-arg VERSION=3.7.1 -t nginx:latest .
``` 
#### Sistemdeki tüm imageleri listeleme:
``` 
docker image ls
``` 
#### Sistemden bir imajı silme:
``` 
docker image rm image:tag
Örnek: docker image rm nginx:latest
``` 
#### Containerdan image yaratma:
``` 
docker commit container_id|ya da|container_ismi image:tag
Örnek: docker commit 12a793b3fec0 ozgurozturknet/img:latest
``` 
#### Image’i bir dosyaya kaybetmek ve kaydedilmiş bir dosyadan image oluşturmak:
``` 
docker save image:tag -o dosyaadi.tar
Örnek: docker save ozgurozturknet/img:latest -o image.tar

docker load -i dosyaadi.tar
Örnek: docker load -i imagecon1.tar
``` 
