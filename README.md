# 🌐 Global Error Center

> A centralized error message management platform for microservice architectures.

**Global Error Center** is a centralized platform for managing error messages in distributed systems.  
It enables all microservices to throw a unified exception type (e.g. `CustomException("SERVICE.CODE")`) and dynamically retrieve localized messages from a shared service.

---

## 📦 Project Structure

This is a **multi-module Maven project**:

---

## 🚀 Features

- Centralized storage of error messages (per code and language)
- Unified exception handling via `CustomException`
- Language-aware error resolution via REST API
- Feign-compatible error message client
- MongoDB-based persistence
- Optional Redis caching layer (future-ready)
- Admin dashboard ready (optional React/Vue UI)

---

## 🧰 Technologies

- Java 17+
- Spring Boot
- MongoDB
- OpenFeign
- Spring Cloud (optional)
- Redis (optional)

---

## 🛠️ Getting Started

### Prerequisites

- Java 17+
- Maven 3.x
- Docker (for MongoDB)

### Clone & Build

```bash
git clone https://github.com/your-org/global-error-center.git
cd global-error-center
mvn clean install

docker run -d --name mongo -p 27017:27017 mongo:6

cd error-message-service
mvn spring-boot:run

cd ../example-service
mvn spring-boot:run

POST http://localhost:8081/messages
Content-Type: application/json

📘 Usage Example
{
  "code": "USER_SERVICE.USER_NOT_FOUND",
  "messages": {
    "en": "User not found",
    "tr": "Kullanıcı bulunamadı"
  }

2. Trigger an exception in example-service

GET http://localhost:8082/test-error
Headers:
  Accept-Language: tr
}
{
  "code": "USER_SERVICE.USER_NOT_FOUND",
  "message": "Kullanıcı bulunamadı"
}


⸻

📌 Roadmap
	•	Centralized error message storage
	•	Feign-based client integration
	•	Redis caching support
	•	Admin dashboard (React)
	•	Kafka-based cache invalidation
	•	Authenticated message editing (RBAC)

⸻

🤝 Contributing

Pull requests and suggestions are welcome. If you want to make significant changes, please open an issue first to discuss your ideas.

⸻

📄 License

This project is licensed under the MIT License. See the LICENSE file for more information.

⸻

👤 Maintainer

Developed and maintained by Bulut Çakan
GitHub Profile
