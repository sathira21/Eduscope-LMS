# Eduscope LMS API Documentation

This document provides a detailed reference for all the API endpoints available in the Eduscope LMS backend.

## Authentication

### POST /api/auth/register
Register a new user.
- **Roles**: student, teacher, admin
- **Body**: `{ name, email, password, role }`

### POST /api/auth/login
Log in an existing user.
- **Body**: `{ email, password }`
- **Response**: `{ success, token, user }`

---

## Quizzes

