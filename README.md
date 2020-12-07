###

A simple Dockerized Spring Boot REST API example. You can build and run whereever you want.

Reference repository : https://github.com/daviestobialex/spring-mysql-redis-cache

Before running docker build, you should checkout and configure Mysql and Redis endpoints that is located in the files below :

***
src/main/resources/application.yml
src/main/java/com/jeonguk/web/config/RedisConfig.java
***

Also, if you want to use simple deployment and service k8s yamls, don't forget to update image line in deployment.yaml. 
Service yaml, whose service type is Load Balancer, has also been annonated in accordance with AWS. Using Annotation is not mandatory. If you don't want to work on AWS and want to use yaml, you can delete it.

###

Usage : 

```
cd spring-mysql-redis-cache/
docker build -t <image_tag> .
```

After deployment,

For testing :

```
// Management

http://<app-url>:91/env
http://<app-url>:91/health
http://<app-url>:91/info
http://<app-url>:91/metrics

// App

Add data : 

curl -d '{"title":"post title", "content":"post content"}' -H "Content-Type: application/json" -X POST http://<app-url>:80/api/posts

data get cache TimeUnit.SECONDS 10 :

curl http://<app-url>:80/api/posts/1
```

