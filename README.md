# Example of how to deploy two springboot applications in Wildfly

This is example how to deploy two springboot application in Wildfly.
Each application has its own configuration that is load from file in Wildfy module.

See more: https://mariusz.wyszomierski.pl/en/deploy-two-springboot-applications-in-wildfly-with-external-properties/

_Warning: this code is only example - do not use it on production!_ 

## How to run

You need:
* java 11
* docker
* docker-compose

Instructions:
* build two applications
```
./service1/gradlew clean build -p service1
./service2/gradlew clean build -p service2
```
* run Wildfly in docker
```
docker-compose -f docker/docker-compose.yml up -d --build
```
* now you can check properties of each application through actuator endpoint  

http://localhost:8080/service1/actuator/env/speedlog.common-name-property  
http://localhost:8080/service1/actuator/env/service1.specific  

http://localhost:8080/service2/actuator/env/speedlog.common-name-property  
http://localhost:8080/service2/actuator/env/service2.specific  