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

