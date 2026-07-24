# Project Architecture

## Overview
WorkSphere Enterprise employs a hybrid polyglot architecture. It utilizes a React frontend, supported by a dual-backend strategy: an Express.js/Node.js API for rapid CRUD operations and real-time sockets, and a Spring Boot (Java) backend for heavy enterprise integrations and background processing.

## Frontend Architecture
- **Framework:** React 18 with Vite.
- **State Management:** Redux Toolkit & Zustand.
- **Routing:** React Router v7 with dynamic, role-based module loading.
- **Styling:** Tailwind CSS with Framer Motion for micro-interactions.

## Backend Architecture
- **Node.js Gateway:** Express.js handling auth, websockets, and fast HR/Telemetry queries.
- **Spring Boot Core:** Java 17 service for robust enterprise transactions, finance batch processing, and complex analytics.
- **ORM:** Prisma (Node.js) & Hibernate (Java).

## Event-Driven Layer
- **Kafka:** Used for high-throughput telemetry (GPS, keystrokes, system vitals) processing.
- **Redis:** Session caching and real-time Socket.io pub/sub.

## Authentication Flow
1. User authenticates via Node.js Gateway.
2. Gateway issues a signed JWT.
3. Frontend stores JWT in HttpOnly cookie/memory.
4. Requests to Java/Node services validate JWT via shared secret/public key.

## Role Based Access (RBAC)
Implemented via a granular permission matrix stored in PostgreSQL. Roles include CEO, HR, Employee, DevOps, Security, etc.

## Deployment Architecture
Dockerized microservices orchestrated via Kubernetes, with Terraform defining the underlying AWS/GCP infrastructure.
