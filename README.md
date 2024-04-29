# Spring Boot Microservice Ecosystem Demo

Demo of microservices ecosystem, making use of Netflix OSS and some microservice design patterns.


#### Services Description
* **Product-Service:** storage of products containing its images, that are sent to Amazon S3 through S3-Service,Implemented using [Netflix Hystrix](https://github.com/Netflix/Hystrix/wiki) for fault tolerance and MongoDB as database.

	http://localhost:8084/
	
* **S3-Service:** responsible for communication with Amazon S3, to upload, delete and get files.
	http://localhost:8083/
	
* **Auth-Server:** authentication of users, delivering a access token, registration of client applications and users, also has the endpoint to get user info like roles and authorities. Implemented with Spring Security and Spring OAuth2.
	http://localhost:8085

* **API-Gateway:** centralized point of access to all service, fetch list of available services from service-discovery. Implemented with [Netflix Zuul](https://github.com/Netflix/zuul).
	http://localhost:8888/

* **Serivce-Discovery:** implemented with [Netflix Eureka](https://github.com/Netflix/eureka).
	http://localhost:8081/
	
	
### Requirements
* Maven
* JDK 1.8

#### Running any service
* mvn spring-boot:run


