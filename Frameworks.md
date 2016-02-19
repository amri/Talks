Frameworks
========
*tl;dr*

Spring (java)
------
- Lightweight alternative to J2EE (achieve capabilities of EJB with simple POCO)
- Initially requires configurations using XML, it has changed ever since:
  - Version 2.5 by using Component based scanning
  - Version 3 by using Annotation
- How to start developing application with Spring:
  1. A project structure, complete with a Maven or Gradle build file including required dependencies. At the very least, you’ll need Spring MVC and the Servlet API expressed as dependencies.
  2. A web.xml file (or a WebApplicationInitializer implementation) that declares Spring’s DispatcherServlet.
  3. A Spring configuration that enables Spring MVC.
  4. A controller class that will respond to HTTP requests with “Hello World”.
  5. A web application server, such as Tomcat, to deploy the application to.

Spring Boot (java/groovy)
----------------
- Suites best with Microservice architecture
- Spring Boot allows developers to start with minimum dependencies to start with Spring Framework
- Capabilities:
  1. Automatic configuration— Spring Boot can automatically provide configuration for application functionality common to many Spring applications. [Spring docs on it](https://docs.spring.io/spring-boot/docs/current/reference/html/using-boot-auto-configuration.html)
  2. Starter dependencies— You tell Spring Boot what kind of functionality you need, and it will ensure that the libraries needed are added to the build. [List of starters](https://github.com/spring-projects/spring-boot/tree/master/spring-boot-starters)
  3. The command-line interface— This optional feature of Spring Boot lets you write complete applications with just application code, but no need for a traditional project build.
  4. The Actuator— Gives you insight into what’s going on inside of a running Spring Boot application.
- What it does not:
  1. Spring Boot is not an application server. It has bare minimum app server (Jetty?)
  2. Spring Boot doesn’t implement any enterprise Java specifications such as JPA or JMS
  3. Spring Boot doesn’t employ any form of code generation to accomplish its magic
- Installing:
  1. Download and extract Spring Boot CLI [v1.3.2](http://repo.spring.io/release/org/springframework/boot/spring-boot-cli/1.3.2.RELEASE/spring-boot-cli-1.3.2.RELEASE-bin.zip)
  2. Set up JAVA_HOME, SPRING_HOME & PATH to include SPRING_HOME\bin
  3. Test with `spring --version`
- Initializing:
  * Option 1: Call `spring init -dweb --build gradle -p war <appname>` `-d: dependencies ... --build: build type ... -p extract as ...`

  * Option 2: Open [Spring Initializer](http://start.spring.io/) site
- Structures:
