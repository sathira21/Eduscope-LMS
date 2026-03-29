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
- **Reporting & Analytics**: Processes raw attempt data into meaningful insights for teachers and administrators.
- **Learning Material Module**: Manages educational resources and student engagement metrics.

## 📡 API Design Philosophy

We follow RESTful design principles for all our endpoints.

- **Stateless**: No server-side session state; JWT tokens carry the necessary identity.
- **HATEOAS (Hypermedia as the Engine of Application State)**: Partial implementation through structured links in JSON responses.
- **Versioning**: Versioning prefix (`/api/v1/...`) to allow for breaking changes in the future.

## 📦 Data Modeling Strategy

Using Mongoose with MongoDB allows us to handle unstructured quiz questions flexibly while maintaining schema integrity for core entities like Users and Attempts.

```javascript
const { Schema, model } = require('mongoose');

const BaseSchema = new Schema({
  createdAt: { type: Date, default: Date.now },
  updatedAt: { type: Date, default: Date.now }
});
