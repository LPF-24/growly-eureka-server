# Eureka Service

`eureka-service` is the **Service Discovery Server** for the **Growly** microservices system. It enables other services to register themselves and discover each other dynamically.

## 📌 Responsibilities

- Acts as the **Eureka Server**
- Provides service registry for clients (e.g. `habit-service`, `auth-service`)
- Required for Spring Cloud service discovery

## 🌐 Access

After starting, the dashboard is available at:

http://localhost:8761


> Default port: `8761` (configured in `application.yml`)

## 🧰 Technologies

- Java 17
- Spring Boot
- Spring Cloud Netflix Eureka
- Docker

## ⚙️ Configuration

Minimal `application.yml`:

```yaml
server:
  port: 8761

spring:
  application:
    name: eureka-server

eureka:
  client:
    register-with-eureka: false
    fetch-registry: false
```

## 🐳 Docker
Use docker-compose as part of the full system
To build and run the container:
```bash
> docker compose up --build eureka-server
```

## 📚 Notes
- Other services register themselves with Eureka using spring.cloud.discovery.enabled=true
- This service does not register itself (standalone registry)
- Required to be up before dependent services start

## 🔗 Related
Part of the [growly-infra](https://github.com/LPF-24/growly-infra) project.

---

> 📡 **eureka-service** — the heartbeat of Growly's service network.
