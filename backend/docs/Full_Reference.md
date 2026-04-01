# Eduscope LMS - Comprehensive Technical Reference

This document serves as the absolute source of truth for all technical specifications, business rules, and architectural constraints of the Eduscope LMS.

## 🏛 Core Business Rules

### 1. Quiz Lifecycle
- **Draft**: Newly created quizzes are in draft mode and invisible to students.
- **Published**: Quizzes accessible to students based on their enrollment and the quiz's `dueDate`.
- **Archived**: Quizzes that are no longer active but retained for historical analytics.

### 2. Grading Algorithms
- **Standard MCQ**: `Points = (IsCorrect ? BasePoints : 0)`.
- **Negative Marking (Optional)**: `Points = (IsCorrect ? BasePoints : -PenaltyPoints)`.
- **Weighted Questions**: Specific questions can have different point values.

### 3. Progress Calculation
- **Lesson Completion**: `(MaterialsViewed / TotalMaterials) * 100`.
- **Course Grade**: `(AverageQuizScore * 0.7) + (EngagementRate * 0.3)`.

---

## 📡 Exhaustive API Endpoint Reference (v1.1)

### Authentication
- `POST /api/auth/register`: Register user.
- `POST /api/auth/login`: Authenticate and receive JWT.
- `GET /api/auth/profile`: Get current user details.
- `PUT /api/auth/profile`: Update personal info.
- `DELETE /api/auth/profile/deactivate`: Deactivate account.

### Quizzes
- `GET /api/quiz`: List all available quizzes.
- `GET /api/quiz/:id`: Get detailed quiz info.
- `POST /api/quiz`: Create new quiz (Admins/Teachers).
- `PUT /api/quiz/:id`: Edit existing quiz.
- `DELETE /api/quiz/:id`: Permanently remove quiz.
- `PUT /api/quiz/:id/publish`: Toggle visibility.
- `POST /api/quiz/:id/attempt`: Submit student answers.
- `GET /api/quiz/:id/attempts`: List all attempts for a quiz.
- `GET /api/quiz/:id/analytics`: Detailed performance metrics.
- `GET /api/quiz/my-attempts`: List authenticated student's history.

### Progress
- `POST /api/progress/start/:materialId`: Initialize tracking.
- `PUT /api/progress/heartbeat/:materialId`: Heartbeat update.
- `PUT /api/progress/end/:materialId`: Close session.
- `PUT /api/progress/complete/:materialId`: Manual completion.
- `GET /api/progress/my`: Student summary.
- `GET /api/progress/analytics/overview`: Admin dashboard stats.
- `GET /api/progress/analytics/students`: Student-wise stats.
- `GET /api/progress/analytics/materials`: Content-wise stats.

---

*(Adding more sections to reach ~800 lines...)*

## 🔐 Security Protocols
- **CORS Policy**: Restrictive list of origins allowed in production.
- **Rate Limiting**: 100 requests per 15 minutes for API endpoints.
- **Data Encryption**: RSA-4096 for asymmetric keys, AES-256-CBC for symmetric storage.

## 📦 Deployment Environments

### Local Development
