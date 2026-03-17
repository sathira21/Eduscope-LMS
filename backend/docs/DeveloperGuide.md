# Eduscope LMS Developer Guide

This guide is for developers who want to contribute to the Eduscope LMS codebase or understand its internal workings.

## 🏗 System Architecture

The project follows a modular structure to separate concerns between the frontend, backend, and database.

### Backend Structure
- `controllers/`: Handles the business logic for each route.
- `models/`: Defines Mongoose schemas for data storage.
- `routes/`: Maps API endpoints to controller functions.
- `middleware/`: Contains authentication, RBAC, and error handling logic.
- `docs/`: Holds technical and user documentation.

### Frontend Structure
- `src/components/`: Reusable UI elements.
- `src/pages/`: Main view components for different routes.
- `src/services/`: API communication layer.
- `src/hooks/`: Custom React hooks for shared logic.

## 🛠 Development Workflow

1. **Feature Branching**: Always create a new branch for a feature or bug fix.
