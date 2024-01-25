# fullstack-assignment
Maveric's assignment for fullstack developers. Candidates are expected to complete this assignment within 48 hrs.

Fork this repository and add the webapp and services code as specified in the README section. Once you are done with the assignment please share the link to your forked repository with our HR team.

Candidates are expected to containerise the entire application and update the  /artefacts/scripts/docker-compose.yml file such that executing `docker-compose up` command should bring up the entire application along with all the dependencies like db etc.

> [!NOTE]
> Pay special attention to the below mentioned points:
> 1) Adhere to JAVA and JavaScript coding best practices. Follow [google coding standards](https://github.com/HPI-Information-Systems/Metanome/wiki/Installing-the-google-styleguide-settings-in-intellij-and-eclipse)
> 2) There must be no critical or blocking SonarQube and SonarLint errors
> 3) Separate feature branches must be there for individual features/endpoints. For example account creation, updation deletion etc must be implemented in their respective branches
> 4) Follow proper folder structure. For frontend seggregrate code based on features where as for springboot services follow the folder structure show in the account-service
> 5) JUNIT and Mockito test cases are a must for backend code with 80% code coverage (eureka and gateway services the exception)
> 6) Every microservice must include a postman collection to test all the endpoints of that particular service
> 7) Endpoints must be testable from both via spring cloud gateway as well as ip:port of the respective service
> 8) All the API request and response must be logged with the proper Correlation ID. Same corelation id needs to be passed across interdependent services for tracing the chained service calls
> 9) Feign client must be used for service to service communication (AccountService->BalanceService)
> 10) All the app components spring cloud gateway, eureka service, Core Microservices, MongoDb, MySQL, webapp must be containerised. Volume mounting to be done whereever necessary
> 11) Pagination needs to be handled for all the list apis as mentioned in the swagger
> 12) API implementation must exactly adhere to the swagger specification (Request, Response, path,query params, error codes etc). There should not be any deviations.
> 13) Data models must have proper validation
> 14) Error handling should be taken care for all the endpoints as per the swagger file
> 15) Look and feel of the webapp should match the Maveric branding guidelines as shown in the wireframe. Pay attention to fonts, spacing, button colors. Check the [**artefacts/resources**](/artefacts/resources) folder for the necessary resources needed for the webapp
> 16) Webapp and all the services must have a README file listing the commands and all the dependencies to run the application

> [!TIP]
> Bonus points will be awarded for securing the APIs via JWT token & implementing the login page

# Problem statement

Build a web application called Maveric Bank enabling bank customers to manage their account information i.e, customer profile, account balance and transaction information.

Follow below mentioned Techstack, Architecture, ER diagram, Wireframe and Swagger to build the application. Check the artefacts folder of this repo for resources and documentation

# Architecture
![maveric-bank-architecture](https://github.com/MAVERIC-ThinkNXT-LIMITED/fullstack-assignment/assets/9525282/9b228fd1-c1d3-4c11-87cc-bd48a231d94e)



# Techstack

Below is the techstack that we will be using in order to build this application

| Application Compoent  | Tech stack |
| ------------- | ------------- |
| Front end  | Angular/ReactJs/VueJs, Jest/Jasmine, Cucumber, Mocha, Chai  |
| Backend  | Java 17, Spring 3.2.2, Maven, Junit, Mockito  |
| Architecture   | Microservice based architecture  |
| SCM  | Git, Github  |
| Deployment  | Docker, DockerCompose  |
| API Gateway  | Spring Cloud Gateway  |
| Service Discovery  | Eureka Server  |
| Logging  | Lombok/SLF4J/Log4J  |
| Database  | MongoDb/MySQL  |
| Backend  | Java 17, Spring 3.2.2  |
| StaticCodeAnalysis  | SonarQube  |
| API Testing  | Postman |
| API Documentation  | Swagger/OpenAPI spec  |

# Application components

|Service name|	Port number|	Git repo / Folder name|	Description |
|------------- | ------------- |------------- | ------------- |
|user-service|	3005|	user-service|	Service for managing users |
|account-service	|3010	|account-service|	Service for managing accounts |
|balance-service	|3015	|balance-service	|Service for managing balances| 
|transaction-service	|3020	|transaction-service	|Service for managing transactions|
|eureka-service	|8761	|eureka-service	|Service for enabling service discovery|
|gateway-service	|8000	|gateway-service	|Service for cloud gateway|
|maveric-bank-webapp	|8080	|maveric- bank-webapp	|Angular/ReactJs/VueJs web application|


# ER Diagram

<img width="894" alt="ER-Diag" src="https://github.com/MAVERIC-ThinkNXT-LIMITED/fullstack-assignment/assets/9525282/6551a03b-db57-413a-8b1c-5d48851def7b">

# Wireframe

![Maveric-Bank-App-Wireframe](https://github.com/MAVERIC-ThinkNXT-LIMITED/fullstack-assignment/assets/9525282/da8bb6f3-991a-4c32-99f2-5b3e0ac91379)

# API Specification
[Link to swagger file](./artefacts/documents/maveric-bank-api.yaml)
