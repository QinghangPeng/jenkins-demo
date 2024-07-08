# Getting Started

### Reference Documentation

For further reference, please consider the following sections:

* [Official Gradle documentation](https://docs.gradle.org)
* [Spring Boot Gradle Plugin Reference Guide](https://docs.spring.io/spring-boot/docs/3.0.3/gradle-plugin/reference/html/)
* [Create an OCI image](https://docs.spring.io/spring-boot/docs/3.0.3/gradle-plugin/reference/html/#build-image)
* [Spring Web](https://docs.spring.io/spring-boot/docs/3.0.3/reference/htmlsingle/#web)
* [OpenFeign](https://docs.spring.io/spring-cloud-openfeign/docs/current/reference/html/)

### Guides

The following guides illustrate how to use some features concretely:

* [Building a RESTful Web Service](https://spring.io/guides/gs/rest-service/)
* [Serving Web Content with Spring MVC](https://spring.io/guides/gs/serving-web-content/)
* [Building REST services with Spring](https://spring.io/guides/tutorials/rest/)

### Additional Links

These additional references should also help you:

* [Gradle Build Scans – insights for your project's build](https://scans.gradle.com#gradle)
* [Declarative REST calls with Spring Cloud OpenFeign sample](https://github.com/spring-cloud-samples/feign-eureka)

### Config Jenkins and connect to local Jenkins through intranet penetration
* Install docker jenkins
```shell
docker run -d --user root -p 9090:8080 -p 50000:50000 -v /var/run/docker.sock:/var/run/docker.sock -v jenkins_home:/var/jenkins_home jenkins/jenkins:jdk17
```
* Install docker to jenkins container
```shell
curl -fsSL https://get.docker.com -o get-docker.sh
sh get-docker.sh
or
curl -fsSL https://get.docker.com -o get-docker.sh | sh
```
* Install plugins for jenkins: Pipeline / Stage View
* Intranet penetration: Use natapp or ngrok
* Config webhook for project on github: Settings -> Webhooks -> Add webhook
* Generate token for Jenkins on github: My Profile -> Settings -> Developer Settings -> Personal access tokens -> Tokens(classic) -> Generate New Token(classic)
* Config token for Jenkins to connect to Github: Manage Jenkins -> System -> Github Servers -> add Credentials -> type choose Secret text
* Add new Item(pipeline item type) on Jenkins: New Item -> input item name -> choose Pipeline item type
* Set up configurations: Github project -> Build Triggers -> Pipeline(choose Pipeline script from SCM)
