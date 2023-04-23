# Weather Forecast Service (WFS)
`weather-forecast-service` is a weather rest api application that provides current weather information and forecasts for various locations.

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
