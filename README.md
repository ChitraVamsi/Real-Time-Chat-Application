# Real-Time Chat Application

Implemented real-time bidirectional communication using WebSocket and STOMP, enabling instant message broadcasting among multiple connected clients.

A real-time chat application built using Spring Boot, WebSocket, STOMP, SockJS, and Thymeleaf. The application enables multiple users to exchange messages instantly through a WebSocket-based communication channel, providing a seamless real-time messaging experience.

## Features

* Real-time messaging using WebSockets
* STOMP protocol for message communication
* SockJS fallback support for browser compatibility
* Multi-user chat communication
* Dynamic message broadcasting
* Responsive user interface with Bootstrap
* Instant message updates without page refresh
* Lightweight and scalable architecture

---

## Tech Stack

### Backend

* Java 17
* Spring Boot
* Spring WebSocket
* STOMP Messaging
* Thymeleaf

### Frontend

* HTML5
* Bootstrap 5
* JavaScript

### Communication Protocols

* WebSocket
* STOMP
* SockJS

### Build Tool

* Maven

---

## Architecture

```text
Client Browser
      │
      ▼
SockJS Connection
      │
      ▼
WebSocket Endpoint (/chat)
      │
      ▼
STOMP Broker
      │
      ▼
ChatController
      │
      ▼
Topic Subscription (/topic/messages)
      │
      ▼
Connected Clients
```

---

## Project Structure

```text
src/main/java
│
├── config
│   └── WebSocketConfig
│
├── controller
│   └── ChatController
│
├── model
│   └── ChatMessage
│
└── AppApplication

src/main/resources
│
├── templates
│   └── chat.html
│
└── application.properties
```

---

## WebSocket Configuration

### Connection Endpoint

```text
/chat
```

### Application Destination Prefix

```text
/app
```

### Topic Subscription

```text
/topic/messages
```

---

## Messaging Flow

### Send Message

Client sends message to:

```text
/app/sendMessage
```

### Receive Messages

All connected clients subscribe to:

```text
/topic/messages
```

### Example Message

```json
{
  "sender": "Vamsi",
  "content": "Hello Everyone!"
}
```

---

## How It Works

1. User opens the chat application.
2. Browser establishes a WebSocket connection using SockJS.
3. Client subscribes to `/topic/messages`.
4. User sends a message.
5. Message is sent to `/app/sendMessage`.
6. Spring Boot processes the message.
7. Message is broadcast to `/topic/messages`.
8. All connected users instantly receive the message.

---

## Installation

### Clone Repository

```bash
git clone https://github.com/ChitraVamsi/Real-Time-Chat-Application.git
```

### Navigate to Project

```bash
cd Real-Time-Chat-Application
```

### Run Application

```bash
mvn spring-boot:run
```

Application will start at:

```text
http://localhost:8080/chat
```

---

## Dependencies

* Spring Boot Starter Web MVC
* Spring Boot Starter WebSocket
* Spring Boot Starter Thymeleaf
* Lombok

---

## Author

**Vamsi Chitra**

GitHub: https://github.com/ChitraVamsi
