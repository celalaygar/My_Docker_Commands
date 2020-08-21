##  Logging

#### Container tarafından oluşturulan logları görmek:
``` 
docker logs container_id|ya da|container_ismi
Örnek: docker logs 12a793b3fec0
``` 
#### Container tarafından oluşturulan logları uzun formatta detaylı görmek:
``` 
docker logs --details container_id|ya da|container_ismi
Örnek: docker logs --details 12a793b3fec0
``` 
#### Container tarafından oluşturulan logları belirli tarih aralığında görmek:
``` 
docker logs --since tarih_saat --until tarih_saat container_id|ya da|container_ismi

Örnek: docker logs --since 2020-01-13T11:34:43.154304300Z 12a793b3fec0 
(since verilen andan itibaren olanları, until ise verilen ana kadar olanları listeler)
``` 
#### Container tarafından oluşturulan logların belirli sayıda son oluşanlarını görmek:
``` 
docker logs --tail sayı container_id|ya da|container_ismi
Örnek: docker logs --tail 10 12a793b3fec0 (son 10 log çıktısını listeler)
``` 
#### Container tarafından oluşturulan logları anlık olarak izlemek:
``` 
docker logs -f container_id|ya da|container_ismi

Örnek: docker logs -f 12a793b3fec0 (loglar oluştukça ekranda gözükecektir. 
Ctrl-C ile bağlantı kesilebilir)
``` 
