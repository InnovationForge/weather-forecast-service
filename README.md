# Weather Forecast Service (WFS)
`weather-forecast-service` is a weather rest api application that provides current weather information and forecasts for various locations.

## WFS Requrements (functional & non-functional)
A weather REST API application should provide accurate, reliable, and timely weather data to its users, while also implementing security and performance best practices to ensure that it is scalable, secure, and easy to use. Some of the specific requirements for this application is based upon are as follows : 

1. Accurate weather data: The most important requirement for a weather REST API application is to provide accurate and up-to-date weather data to its users. This includes current temperature, precipitation, wind speed and direction, humidity, and other weather-related metrics.
2. Geolocation support: The API should support geolocation-based queries, which allow users to retrieve weather data for a specific location based on its latitude and longitude coordinates.
3. Historical weather data: The API should be able to provide historical weather data for a specific location, which allows users to analyze trends and patterns over time.
4. Data format: The API should provide weather data in a standard format, such as JSON or XML, which makes it easy for developers to integrate the API into their applications.
5. Authentication and authorization: The API should support authentication and authorization mechanisms to ensure that only authorized users can access the weather data.
6. Rate limiting: The API should implement rate limiting to prevent users from making too many requests too quickly, which can overload the API and impact its performance.
7. Documentation: The API should provide comprehensive documentation that describes the available endpoints, parameters, and response formats, as well as guidelines for using the API and best practices for integrating it into applications.
8. Scalability and availability: The API should be designed to be scalable and highly available, with redundant servers and load balancing mechanisms to ensure that it can handle large volumes of requests and provide consistent performance.

## WFS System architecture
WFS system architecture involves identifying the components and their interactions. This includes defining the logical and physical architecture, as well as selecting the appropriate deployment and integration strategies.

## WFS Technology stack
We selected the following WFS technology stack that will be used to implement the application. This includes selecting programming languages, frameworks, libraries, and tools based on the WFS requirements and the WFS system architecture
* Java SE 17
* Spring Boot 3.0.6
* Maven 3.8.6

Other associated technologies from Spring Cloud
* Spring Cloud Gateway
* Spring Cloud Config
* Spring Cloud Circuit Breaker
* Spring Cloud Contract

## WFS Maven Project Structure
WFS Rest API application is a multi-module Maven project that contains more than one module or sub-project. The main benefit of using a multi-module Maven project is that it allows you to divide a large project into smaller, more manageable modules. Each module can have its own dependencies, build configurations, and release cycles, which makes it easier to manage and maintain the project `weather-forecast-service`.  <br>Here is the maven project structure : 
```bash
weather-forecast-service
    ├───wfs-application
    ├───wfs-library
    ├───wfs-gateway-server
    ├───wfs-config-server
    ├───wfs-stub-server
    ├───.gitignore
    ├───pom.xml
    └───README.md
```
### wfs-application module
`wfs-application module` is the application module, that implements the business functionality of weather API that provides current weather information and forecasts for various locations.
### wfs-library module
`wfs-library` is the library module created with the vision of re-usability of its functionality in other applications/modules, One or more library modular design is a best practice to improve the design process by allowing better re-usability, workload handling, and easier debugging processes.
### wfs-gateway-server module
`wfs-gateway-server` is an application, that works as an API Gateway built on top of Spring WebFlux. It is meant to provide a simple, yet effective way to route to APIs and provide cross cutting concerns to them such as: security, monitoring/metrics, and resiliency.
### wfs-config-server module
`wfs-config-server module` is an application built on Spring Cloud Config. It provides support for externalized configuration. With the Config Server you have a central place to manage external properties for applications across all environments.
* dev
* test
* prod
### wfs-stub-server module
`wfs-stub-server module` is an application built using WireMock and Spring Boot. it helps in Service virtualization. I believe , haveing a stub server as part of the application offers a great best practice to simulate the behavior of external or integrated services on which the system is dependent. It ensures that the system to be tested is isolated by minimizing dependencies. The virtualization of these dependent services, which are beyond our control, will greatly speed up the testing and development processes. In addition to this, possible data-based problems are prevented. Thus, both system dependencies and effects on associated systems are minimized.
