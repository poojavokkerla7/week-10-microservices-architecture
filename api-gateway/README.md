# API Gateway Service

This is the API Gateway for the Microservices Architecture project built using Spring Cloud Gateway.

## Overview
The API Gateway acts as a single entry point for all client requests and routes them to appropriate microservices like User Service, Order Service, etc.

It also provides:
- Centralized routing
- Load balancing via Eureka
- Request filtering
- Service discovery integration

---

## Tech Stack
- Java
- Spring Boot
- Spring Cloud Gateway
- Spring Cloud Netflix Eureka Client
- Maven

---

## Features
- Dynamic routing using service discovery
- Integration with Eureka Server
- Load-balanced requests to services
- Pre/Post filters (optional customization)

---

## Routes Configuration Example
```yaml
spring:
  cloud:
    gateway:
      routes:
        - id: user-service
          uri: lb://USER-SERVICE
          predicates:
            - Path=/users/**
