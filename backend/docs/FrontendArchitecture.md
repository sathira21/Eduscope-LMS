# Eduscope LMS Frontend Architecture

This document provides a technical overview of the React frontend architecture for the Eduscope LMS.

## 🎨 Unified Design System

We use a custom design system built on top of Tailwind CSS for consistent styling across all user-facing pages.

### Core Principles
- **Clarity**: High contrast and readable typography.
- **Hierarchy**: Clear visual distinctions between different types of information.
- **Consistency**: Reusable components for common UI patterns.

## 📁 Component Organization

Components are organized by their scope and purpose.

- **Layouts/**: Wrapper components for global structures like headers and sidebars.
- **Common/**: Generic, highly reusable components like `Button`, `Card`, `Modal`, and `Badge`.
- **Features/**: Business-specific components grouped by functionality (e.g., `QuizPlayer`, `StudentChart`).
- **Pages/**: View components that map directly to application routes.

## 🏗 State Management

We use a hybrid approach to manage state:
