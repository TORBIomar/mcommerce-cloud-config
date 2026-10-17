# ☁️ M-Commerce Cloud Config — Centralized Microservices Configuration

<div align="center">

[![Spring Cloud](https://img.shields.io/badge/Spring%20Cloud-2023.x-6DB33F?style=for-the-badge&logo=spring&logoColor=white)](https://spring.io/projects/spring-cloud)
[![Eureka Server](https://img.shields.io/badge/Service%20Discovery-Netflix%20Eureka-green?style=for-the-badge)]()
[![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.x-6DB33F?style=for-the-badge&logo=springboot&logoColor=white)](https://spring.io)

<p align="center">
  <b>Centralized external configuration repository for distributed M-Commerce microservices.</b><br>
  Powers runtime configuration, environment profiles (dev, test, prod), and dynamic property reloads across services.
</p>

</div>

---

## 🏗️ Architecture

```mermaid
graph TD
    ConfigRepo[(mcommerce-cloud-config)] -->|Git Backend| ConfigServer[Spring Cloud Config Server]
    ConfigServer -->|Externalized Properties| Eureka[Eureka Discovery Server]
    ConfigServer -->|Externalized Properties| Products[Product Microservice]
    ConfigServer -->|Externalized Properties| Orders[Order & Payment Microservices]
```

---

## ⚙️ Managed Configurations

| Property File | Service Name | Role |
|---|---|---|
| `eureka-server.properties` | Eureka Discovery Server | Standalone registry port, peer replication flags, and health settings |
| `microservice-produits.properties` | Product Microservice | Catalog endpoints, DB bindings, and fallback properties |

---

## 🚀 Usage in Spring Boot

In your microservice's `application.properties` / `bootstrap.properties`:

```properties
spring.application.name=microservice-produits
spring.config.import=optional:configserver:http://localhost:9101
```

---

## 👨‍💻 Author

**Omar Torbi** — Full-Stack Engineer & Software Architect
- 🌐 **Portfolio**: [omartorbi.engineer](https://www.omartorbi.engineer)
- 💼 **LinkedIn**: [linkedin.com/in/omar-torbi](https://www.linkedin.com/in/omar-torbi-b8340933a/)
- 🐙 **GitHub**: [@TORBIomar](https://github.com/TORBIomar)
- ✉️ **Email**: [torbi.dev@outlook.com](mailto:torbi.dev@outlook.com)
