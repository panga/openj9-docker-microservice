# Java Microservice running inside Docker with OpenJ9 JVM

Sample SpringBoot 2 microservice with a simple REST resource implementation.

Docker image is using OpenJ9 JVM with optimized settings for Docker.

We are using a 128m max heap size here, you should tweak memory values in case of bigger applications.

BTW do you remember the last time you ran any Java application with 128m max heap size? :)

## Build Java Microservice
``mvn -f microservice/pom.xml package``

## Build Docker Image
``docker-compose build``

## Run Microservice in Docker
``docker-compose up -d``

## Scale Microservice to N instances
``docker-compose up -d --scale app=N``

## Results with OpenJ9

- First container startup:
``Started DemoApplication in 4.143 seconds (JVM running for 4.949)``

- Second container startup:
``Started DemoApplication in 1.116 seconds (JVM running for 1.382)``

- Container memory usage after startup:
``56 MB``

- Container memory usage after 10min load:
``66 MB``

## Results with OpenJDK 9 (for comparison)

- First container startup:
``Started DemoApplication in 1.941 seconds (JVM running for 2.423)``

- Second container startup:
``Started DemoApplication in 1.606 seconds (JVM running for 1.932)``

- Container memory usage after startup:
``193 MB``

- Container memory usage after 10min load:
``241 MB``
