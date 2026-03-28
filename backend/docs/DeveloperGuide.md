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
   ```bash
   git checkout -b feature/cool-new-thing
   ```
2. **Linting**: Run ESLint to ensure code quality.
3. **Pre-commit Hooks**: We use Husky for automatic linting before each commit.

## 🔐 Security Best Practices

### Authentication
- Passwords must be hashed using BCrypt before storing.
- JWT tokens should have a reasonable expiration time.
- Always use HTTPS in production.

### Data Validation
- Sanitize all user inputs to prevent XSS and SQL/NoSQL injection.
- Use Mongoose validation schemas for database integrity.

## 🧪 Testing Guidelines

- **Unit Tests**: Test individual functions and handlers.
- **Integration Tests**: Test the interaction between several modules.
- **E2E Tests**: Use Cypress or Playwright for critical user flows.

## 📜 Coding Style

- Use `camelCase` for variable and function names.
- Use `PascalCase` for React components and Classes.
- Use `UPPER_CASE` for constants and environment variables.

---
