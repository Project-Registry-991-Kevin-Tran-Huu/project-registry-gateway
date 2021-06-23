# project-registry-gateway

## Project Description
This is a microservice representation of the Project Registry Backend. This microservice contains the Spring Cloud Gateway code.

## Technologies Used
* Java 8
* Spring Boot
* Spring MVC
* Spring AOP
* Spring Data
* JUnit
* Mockito
* AWS S3
* PostgreSQL
* Jenkins

## Features
* Provides gateway services for the microservices

To-do List:
* 

## Usage

# Running Locally
#### Before running this application as a Spring Boot App, have docker installed on your machine and have an instance of consul running. Instructions for this setup follow.
* install docker desktop on your machine
* run the following commands to pull in consul from docker hub and to get it running:
*   docker pull consul
*   docker run -d --name consul -p 8500:8500 consul
*   docker start consul

#### Gateway
* git clone https://github.com/Project-Registry-991-Kevin-Tran-Huu/project-registry-gateway
* Run this project in Eclipse or SpringToolSuite
* Do a Maven update to import the dependencies needed from the pom.xml
* Launch a Consul instance from a Docker container on port 8500
* Launch this application using spring boot.
* This app will run at http://localhost:8085

# Docker Image
