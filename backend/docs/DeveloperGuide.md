# Eduscope LMS Developer Guide

This guide is for developers who want to contribute to the Eduscope LMS codebase or understand its internal workings.

## 🏗 System Architecture

The project follows a modular structure to separate concerns between the frontend, backend, and database.

### Backend Structure
- `controllers/`: Handles the business logic for each route.
- `models/`: Defines Mongoose schemas for data storage.
