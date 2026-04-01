# Eduscope LMS Database Schema

This document provides a detailed breakdown of the MongoDB collections and their schemas used in the Eduscope LMS.

## Collections Overview

### 1. Users
Stores information about students, teachers, and admins.
- `name`: String, required.
- `email`: String, required, unique.
- `password`: String, required (hashed).
- `role`: String, enum: ['student', 'teacher', 'admin'], default: 'student'.
- `studentId`: String, unique (for students).
- `isActive`: Boolean, default: true.
- `lastLogin`: Date.

### 2. Quizzes
Stores quiz definitions and questions.
- `title`: String, required.
- `description`: String.
- `subject`: String.
- `module`: String.
- `questions`: Array of objects.
    - `question`: String, required.
    - `type`: String, enum: ['mcq', 'true_false', 'short_answer'].
    - `options`: Array of Strings (for MCQs).
    - `correctAnswer`: String.
    - `explanation`: String.
    - `points`: Number, default: 5.
- `timeLimit`: Number (minutes).
- `passingScore`: Number (percentage).
- `isPublished`: Boolean, default: false.
- `createdBy`: Reference to User.

### 3. QuizAttempts
Stores student results for each quiz attempt.
- `quiz`: Reference to Quiz.
- `student`: Reference to User.
- `answers`: Array of objects.
    - `questionId`: Reference.
    - `answer`: String.
    - `isCorrect`: Boolean.
    - `pointsEarned`: Number.
- `score`: Number.
- `totalPoints`: Number.
- `percentage`: Number.
- `passed`: Boolean.
- `startedAt`: Date.
- `submittedAt`: Date.
- `timeSpent`: Number (seconds).

### 4. ContentProgress
Tracks student engagement with course materials.
- `student`: Reference to User.
- `material`: Reference to Material.
- `course`: Reference to Course.
- `status`: String, enum: ['not_started', 'in_progress', 'completed'].
- `viewCount`: Number.
