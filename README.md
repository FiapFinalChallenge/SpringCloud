# Spring Cloud Gateway

This project is a Spring Cloud Gateway instance configured to act as an intelligent API gateway. It routes requests to microservices based on their registration with a Eureka service discovery server.

## Prerequisites

* Java 17 or later
* Maven or Gradle
* Docker

## Building the Project

1. Clone this repository.
2. Navigate to the project directory:
   ```bash
   cd spring-cloud-gateway
    ```
3. Build the project with Maven:
   ```bash
   mvn clean install
    ```

## Running with Docker

1. Build the Docker image:
   ```bash
   docker build -t my-spring-cloud-gateway .
   ```

2.  Run the Docker container:
   ```bash
   docker run -d --name my-spring-cloud-gateway --network my-network -p 8080:8080 my-spring-cloud-gateway
   ```

* Access the Spring Cloud Gateway at: http://localhost:8080

The --network my-network argument in the Docker run command is crucial for ensuring that your Spring Cloud Gateway and the Eureka server can communicate with each other, as well as with any microservices running in Docker containers. This requires that a Docker network named my-network exists. 
If it does not exist, you can create it by running:
   ```bash
   docker network create my-network
   ```