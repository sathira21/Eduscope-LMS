# Eduscope LMS Frontend Design System

This document outlines the visual language and component architecture for the Eduscope LMS frontend.

## 🎨 Token Colors

### Brand Colors
- **Primary**: `#3B82F6` (Electric Blue) - Used for call-to-actions and main brand elements.
- **Secondary**: `#10B981` (Success Green) - Used for progress bars and success messages.
- **Accent**: `#F59E0B` (Warning Amber) - Used for notifications and highlights.

### Semantic Colors
- **Error**: `#EF4444` (Crimson Red)
- **Neutral/Text**: `#1F2937` (Charcoal)
- **Background**: `#F9FAFB` (Subtle Grey)

## 🧊 Visual Style: Glassmorphism

The dashboard uses a modern glassmorphic look for elevated components.

```css
.glass-card {
    background: rgba(255, 255, 255, 0.7);
    backdrop-filter: blur(10px);
    border: 1px solid rgba(255, 255, 255, 0.125);
    border-radius: 1rem;
    box-shadow: 0 8px 32px 0 rgba(31, 38, 135, 0.07);
}
```

## 🏗 Component Hierarchy

1. **Atoms**: Buttons, Inputs, Badges, Tooltips.
2. **Molecules**: Form Fields, Quiz Question Cards, Notification Items.
3. **Organisms**: Sidebar Navigation, Navbar, Quiz Attempt Interface, Analytics Graphs.
4. **Templates**: Dashboard Layout, Auth Layout, Detail Layout.

## ✍️ Typography

- **Headings**: Inter / Outfit (Sans-serif)
- **Body**: Roboto / Open Sans
- **Monospace**: JetBrains Mono (For code snippets)

## 📱 Responsiveness

- **Mobile**: Single column layout with bottom navigation or hamburger menu.
- **Tablet**: Sidebar collapses to icons. 2-column grid for cards.
- **Desktop**: Full sidebar. 3-4 column grid for dashboards.

## 🎞 Animations

- **Hover Effects**: Subtle scaling (1.02x) and shadow deepening.
- **Page Transitions**: Simple fade-in and slide-up.
- **Loading States**: Shimmer effect on skeleton loaders.
