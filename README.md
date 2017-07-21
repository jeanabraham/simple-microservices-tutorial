
A [good hands-on intro](https://developers.redhat.com/promotions/microservices-for-java-developers/) to Microservices development by @christian-posta.

On Mac OS X, install Spring CLI:

```
$ brew tap pivotal/tap
$ brew install springboot
```

Create Spring MVC project and bring it up:

```
$spring init --build maven --groupId com.jeanabraham.examples --version 1.0 --java-version 1.8 --dependencies web --name hola-springboot hola-springboot
$cd hola-springboot
$mvn spring-boot:run
```

For metrics and other cool beans, add the actuator dependency to pom.xml:
```
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-actuator</artifactId>
</dependency>
```

Note: The actuator endpoints are unauthorized by default. This can be circumvented with the below two properties.

```
management.context-path=/actuator
management.security.enabled=false
```

Try out actuator endpoints:
http://localhost:8080/actuator/beans 
http://localhost:8080/actuator/env
http://localhost:8080/actuator/health 
http://localhost:8080/actuator/metrics 
http://localhost:8080/actuator/trace
http://localhost:8080/actuator/mappings