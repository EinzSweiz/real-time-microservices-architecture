# real-time-microservices-architecture
Root repository for event-driven, real-time microservices architecture with multiple independent services.

---

## 🚀 Tech Stack

- Kafka
- gRPC
- Redis
- WebSockets
- RabbitMQ
- MongoDB
- Celery
- FastAPI
- Celery
- Docker + Docker Compose

---

## Microservices Overview

This repository houses multiple microservices that work together as part of an event-driven architecture:

- [Notification Center](https://github.com/EinzSweiz/notification-center) – Real-time notification hub via WebSocket.
- [Notification Consumer](https://github.com/EinzSweiz/notification-consumer) – Consumes item events and processes notifications.
- [Item Microservice](https://github.com/EinzSweiz/item-microservice) – Handles item creation and updates, emitting events to Kafka.

---

## 🧠 Architecture Flow
1. **Item Service** creates events and publishes to Kafka.
2. **Notification Consumer** listens to Kafka and sends notifications to **Notification Center** via gRPC.
3. **Notification Center** pushes notifications to frontend via **WebSocket**.

---

## 📡 Event Flow
- Kafka → Notification Consumer → gRPC → Notification Center → WebSocket → Frontend

---

## 🏗️ Running Locally

Make sure these services are up:
- ✅ Kafka
- ✅ Zookeeper
- ✅ RabbitMQ
- ✅ Redis
- ✅ SMTP (or mock like MailHog)

Then, run:
```bash
docker-compose up --build
