# Eduscope LMS Architecture Deep Dive

This document explains the core architectural principles and technical decisions behind the Eduscope LMS backend.

## 🏗 Modular Monolith Pattern

The project is structured as a modular monolith to balance development speed with logical separation.

### Advantages
- **Shared Memory**: Faster communication between modules than microservices.
- **Simplified Deployment**: All services are packaged and deployed together.
- **Data Consistency**: Direct database access with atomic transactions within a single service.

### Module Breakdown
- **Identity & Access Management (IAM)**: Handles authentication, session management, and role-based permissions.
- **Quiz Management Service**: Manages quiz entities, question logic, and content lifecycle.
