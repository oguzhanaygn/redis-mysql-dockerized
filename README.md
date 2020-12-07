Basit bir Dockerized Spring Boot REST API uygulamasi.

spring-mysql-redis-cache klasorunun icinde Dockerize edilmis hali mevcut, build aldıktan sonra, istediğiniz Docker Registry'e pushlayarak kullanabilirsiniz. Repo ve tag ismine gore deployment yml da degismeli.

Referans repo : https://github.com/daviestobialex/spring-mysql-redis-cache

UYARI :

Uygulama tarafinda configure edilmis MySQL ve Redis endpointlerine dikkat ediniz !
Asagidaki filelarin icerisindeki endpointler sizin infrastructure'iniza uygun olmayabilir, bu durumda uygulama ayaga kalkmayacak ve deneme sureci basarisiz olacaktir.

Endpointlerin duzenlenecegi filelar :

src/main/resources/application.yml
src/main/java/com/jeonguk/web/config/RedisConfig.java

Eğer basitçe oluşturulmuş olan deployment ve servis k8s yaml'ları da kullanmak isterseniz, deployment.yaml içerisinde bulunan image kısmını değiştirmeyi unutmayınız. Servis tipi Load Balancer olan Servis yaml'ın da annonation'ları AWS'e uygun şekilde düzenlenmiştir. Annotation kullanmak zorunlu değildir. AWS üzerinde çalışmayıp yaml'ı kullanmak istiyorsanız silebilirsiniz.


A simple Dockerized Spring Boot REST API example. You can build and run whereever you want.

Reference repository : https://github.com/daviestobialex/spring-mysql-redis-cache

Achtung ! :

Before running docker build, you should checkout and configure Mysql and Redis endpoints that is located in the files below :

src/main/resources/application.yml
src/main/java/com/jeonguk/web/config/RedisConfig.java

Also, if you want to use simple deployment and service k8s yamls, don't forget to update image line in deployment.yaml. 
Service yaml, whose service type is Load Balancer, has also been annonated in accordance with AWS. Using Annotation is not mandatory. If you don't want to work on AWS and want to use yaml, you can delete it.

Usage : 

```
cd spring-mysql-redis-cache/
docker build -t <image_tag> .
```

