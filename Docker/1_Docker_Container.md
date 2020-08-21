orjinal link : https://cafe.ayti.tech/t/docker-cheat-sheet-turkce/228
## Container
#### Container çalıştırma:
``` 
docker container run image:tag
Örnek: docker container run nginx:latest
``` 
#### Detach modda container çalıştırma (-d):
``` 
docker container run -d image:tag
Örnek: docker container run -d nginx:latest
``` 
#### Varsayılan uygulama yerine başka uygulama ile container başlatma:
``` 
docker container run image:tag uygulama
Örnek: docker container run ubuntu:latest ping 127.0.0.1
``` 
#### Container’a bir isim vererek çalıştırma
``` 
docker container run --name isim image:tag
Örnek: docker container run --name container1 -d nginx:latest
``` 
#### Çalışan bir container içerisinde başka bir uygulama çalıştırma:
``` 
docker container exec container_id|ya da|container_ismi uygulama
Örnek: docker container exec 12a793b3fec0 ping 127.0.0.1
``` 
#### Çalışan bir container’a shell bağlantısı oluşturma:
``` 
docker container exec -it container_id|ya da|container_ismi sh
Örnek: docker container exec -it 12a793b3fec0 sh
``` 
#### Container’ı detach modda ve shell bağlantısı ile oluşturma (dit):
``` 
docker container run -dit image:tag sh
Örnek: docker container run -dit nginx:latest sh
``` 
#### Detach modda ve shell bağlantısı ile oluşturulmuş container’a bağlanma:
``` 
docker attach container_id|ya da|container_ismi
Örnek: docker attach 12a793b3fec0
``` 
#### Container durdurma:
``` 
docker container stop container_id|ya da|container_ismi
Örnek: docker container stop 12a793b3fec0
``` 
#### Container silme:
``` 
docker container rm container_id|ya da|container_ismi
Örnek: docker container rm 12a793b3fec0
``` 
#### Çalışan containerı silme (-f):
``` 
docker container rm -f container_id|ya da|container_ismi
Örnek: docker container rm -f 12a793b3fec0
``` 
#### Container kapatıldığı zaman aynı zamanda silinmesi (-rm):
``` 
docker container run -rm image:tag
Örnek: docker container run -rm nginx:latest (-rm ile container kapandığı zaman otomatik olarak silinmesini söylüyoruz)
``` 
#### Container ile ilgili detayları inceleme:
``` 
docker container inspect container_id|ya da|container_ismi
Örnek: docker container inspect 12a793b3fec0
``` 
#### Sistemdeki tüm containerları (çalışan ve durdurulmuş) silme
``` 
docker container rm -f $(docker ps -aq)
``` 
#### Sistemdeki çalışan containerları listeleme:
``` 
docker container ls 
docker container ps
``` 
#### Sistemdeki tüm containerları listeleme:
``` 
docker container ls -a 
docker container ps -a
``` 
#### Çalışan container’daki processleri listeleme:
``` 
docker top container_id|ya da|container_ismi
Örnek: docker top 12a793b3fec0
``` 
#### Çalışan container’ın Cpu, Ram, I/O kullanımını görme:
``` 
docker stats container_id|ya da|container_ismi
Örnek: docker stats 12a793b3fec0
``` 
#### Container’ın memory kullanımını sınırlama (–memory, --memory-swap):
``` 
docker container run --memory=rakam(b,k,m,g) --memory-swap=rakam(b,k,m,g) image:tag

Örnek: docker container run --memory=1g --memory-swap=2g nginx:latest 
(memory-swap ile swap alanı da tanımlayabiliriz.b=byte k=kilobyte m=megabyte g=gigabyte)
``` 
#### Container’ın cpu kullanımını sınırlama (–cpus, --cpuset-cpus):
```
docker container run --cpus="core_adeti" image:tag
Örnek: docker container run --cpus="3" nginx:latest (sistemden kaç core’a erişebileceğini belirledik)

docker container run --cpuset-cpus="core_numarası" image:tag
Örnek: docker container run --cpuset-cpus="0,4" nginx:latest (sistemdeki hangi corelara erişebileceğini belirledik) 
``` 
#### Container’a enviroment variable tanımlama:
``` 
docker container run --env enviroment_variable=değeri image:tag
Örnek: docker container run --env VAR1=deneme1 --env VAR2=deneme2 nginx:latest
``` 
#### Containerdan hosta ya da tam tersi dosya kopyalama:
``` 
docker cp container_id|ya da|container_ismi:path host_path
Örnek: docker cp 12a793b3fec0:/usr/src/uygulama/ .
``` 
