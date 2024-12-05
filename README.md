# Banking Microservices Platform

A microservices-based platform designed to manage physical banking channels (ATMs, POS terminals, branches) and customer operations. The platform provides secure APIs, asynchronous communication, and modular architecture to ensure scalability and reliability.

---

## Project Overview

This project implements a microservices architecture to support the physical channels and operations domain of a banking system. Each service is developed independently, ensuring scalability, flexibility, and seamless integration.

---

## Features

- **Channels Management:**  
  Manage ATMs, POS terminals, and branch offices, including registration, status tracking, and updates.

- **Customer Operations:**  
  Handle customer account management, PIN validation, and profile updates.

- **Transactions Processing:**  
  Support for withdrawals, deposits, and fund transfers with real-time updates.

- **Notification System:**  
  Notify customers via SMS or email about transaction statuses.

- **Auditing and Logging:**  
  Maintain detailed logs of operations for auditing and monitoring.

- **API Gateway:**  
  Centralized request routing with enhanced security and authentication.

- **Service Discovery:**  
  Automatic service registration and load balancing.

- **Caching with Redis:**  
  Redis is used for caching frequently accessed data to enhance performance.

---

## Technical Specification

### Microservices

1. **Channels Service**
   - Endpoints:
     - `POST /channels` – Register a new channel.
     - `GET /channels` – Retrieve all channels.
     - `PUT /channels/{id}` – Update channel details.
     - `DELETE /channels/{id}` – Delete a channel.

2. **Transactions Service**
   - Endpoints:
     - `POST /transactions/withdraw` – Process withdrawals.
     - `POST /transactions/deposit` – Process deposits.
     - `POST /transactions/transfer` – Handle fund transfers.

3. **Customer Service**
   - Endpoints:
     - `POST /customers` – Register a new customer.
     - `GET /customers/{id}` – Retrieve customer details.
     - `POST /customers/verify` – Validate customer PIN.

4. **Notification Service**
   - Asynchronous communication via RabbitMQ to notify customers about transactions.

5. **Auditing Service**
   - Logs user activities and transaction details for auditing.

---

## Non-Functional Requirements

- **Performance:** API response times under 200ms.
- **Security:** JWT-based authentication and TLS encryption.
- **Scalability:** Horizontal scaling of services.
- **Reliability:** 99.9% system uptime.
- **Test Coverage:** Minimum of 80%.
- **Database Migration:** Liquibase is used for database schema versioning and management.

---

## Development Workflow

### Git Flow

The project follows a **Git Flow** that includes the following branches:

1. **develop:**  
   - Active development happens here.
   - All new features and bug fixes are implemented in this branch.

2. **preprod:**  
   - Code from the `develop` branch is merged here for testing in a staging environment.  
   - All functionalities and fixes are tested before moving to production.

3. **prod:**  
   - Contains the final, stable, and production-ready code.  
   - Only thoroughly tested code from `preprod` is merged into this branch.

---

## Tech Stack

- **Programming Language:** Java  
- **Frameworks:** Spring Boot, Spring Cloud  
- **Database:** PostgreSQL  
- **Caching:** Redis  
- **Message Broker:** RabbitMQ  
- **Database Migration:** Liquibase  
- **Monitoring Tools:** Prometheus, Grafana  
- **Logging:** ELK Stack (ElasticSearch, Logstash, Kibana)

---


