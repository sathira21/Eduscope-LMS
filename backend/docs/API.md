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

### GET /api/quiz
Get all quizzes (filtered by role and permissions).
- **Query Params**: `subject, module, search, filter, page, limit`

### GET /api/quiz/:id
Get a specific quiz.
- **Permissions**: All authenticated users (students see restricted views if not attempted).

### POST /api/quiz
Create a new quiz.
- **Roles**: admin, teacher
- **Body**:
  ```json
  {
    "title": "Introduction to Web Development",
    "description": "Basics of HTML, CSS, and JS",
    "subject": "Computing",
    "module": "Web Design",
    "questions": [
      {
        "question": "What does HTML stand for?",
        "type": "mcq",
        "options": ["Hyper Text Markup Language", "High Tech Multi Language"],
        "correctAnswer": "Hyper Text Markup Language",
        "points": 5
      }
    ],
    "timeLimit": 30,
    "passingScore": 50
  }
  ```

### PUT /api/quiz/:id
Update an existing quiz.
- **Roles**: admin, teacher

### DELETE /api/quiz/:id
Delete a quiz.
- **Roles**: admin, teacher

### POST /api/quiz/:id/attempt
Submit a quiz attempt.
- **Roles**: student
- **Body**: `{ answers: [{ questionId, answer }], startedAt, timeSpent }`

### GET /api/quiz/:id/analytics
Get detailed analytics for a quiz.
- **Roles**: admin, teacher

---

## Progress Tracking

### POST /api/progress/start/:materialId
Start tracking progress for a material.
- **Roles**: student

