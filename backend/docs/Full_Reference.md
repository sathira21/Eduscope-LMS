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
