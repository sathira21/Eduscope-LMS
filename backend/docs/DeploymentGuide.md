# Eduscope LMS Deployment Guide

This guide provides step-by-step instructions for deploying the Eduscope LMS to staging and production environments.

## 🚀 Deployment Overview

The project is designed to be easily deployable using modern containerization and cloud platforms.

### Target Environments
- **Staging**: Used for final testing and walkthroughs.
- **Production**: Accessible to all students and teachers.

## 🛠 Prerequisites
- **Node.js**: v18+
- **MongoDB**: Atlas or a local instance version 5.0+.
- **NPM**: v8+

## 🚢 Deployment Steps

### 1. Build the Frontend
```bash
cd frontend
npm install
npm run build
```
This generates the static files in the `/dist` directory.

### 2. Prepare the Backend
```bash
cd backend
npm install
```

### 3. Configure Environment Variables
Ensure all necessary variables are set in the environment:
- `PORT`: Server listening port.
- `MONGO_URI`: Connection string for the database.
- `JWT_SECRET`: Secret key for signing tokens.

### 4. Process Management
We recommend using PM2 to manage the backend process in production.
```bash
pm2 start server.js --name eduscope-backend
```

## 🌐 Serving the Application

### Using Nginx as a Reverse Proxy
