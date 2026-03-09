# Resume Processing System

A distributed resume processing system built using **Spring Boot Microservices** and **Kafka**.

The system allows users to upload resumes, process them asynchronously, extract skills, detect candidate domain, and notify users when processing is complete.

---

## Architecture

User → API Gateway → Job Service → Kafka → Worker Service → Notification Service

---

## Microservices

### 1. Eureka Server
Service discovery for all microservices.

### 2. API Gateway
Single entry point for all client requests.

### 3. Job Service
Handles:
- Resume upload
- Job creation
- Kafka event publishing

### 4. Worker Service
Handles:
- Kafka job consumption
- Resume parsing
- Skill extraction
- Domain detection

### 5. Notification Service
Handles:
- Job completion events
- Sending notifications

---

## Technologies Used

- Java
- Spring Boot
- Spring Cloud Gateway
- Eureka Service Discovery
- Apache Kafka
- PostgreSQL
- MinIO (S3 compatible storage)
- Docker

---

## System Flow

1. User uploads resume.
2. Job Service stores resume in MinIO.
3. Job Service saves job in database.
4. Job Service publishes event to Kafka.
5. Worker Service processes resume.
6. Skills and domain are detected.
7. Job status updated in database.
8. Notification Service sends completion notification.

---

## Project Structure


---

## Future Improvements

- Retry mechanism for failed jobs
- Dead Letter Queue (DLQ)
- Monitoring with Prometheus & Grafana
- Authentication using JWT

---

## Author

Naresh
