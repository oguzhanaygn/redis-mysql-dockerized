FROM maven:3-alpine AS build-project
RUN mkdir -p /opt/demo
COPY . /opt/demo
WORKDIR /opt/demo
RUN mvn clean package -DskipTests=true

FROM openjdk:8-jre-alpine
EXPOSE 8080 8091
WORKDIR /
COPY --from=build-project /opt/demo/target/spring-mysql-redis-cache-0.0.1-SNAPSHOT.jar ./spring-mysql-redis-cache-0.0.1-SNAPSHOT.jar
CMD ["java" ,"-jar", "spring-mysql-redis-cache-0.0.1-SNAPSHOT.jar"]
