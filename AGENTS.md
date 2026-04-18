# Project Overview

This is a personal portfolio website built with React using react-scripts.

The site is component-based and driven by structured data files in `/src/data`.
The primary goal is to maintain a clean, responsive, and consistent UI while keeping content easy to update.

---

# Architecture Summary

## App Flow

- `src/index.js` → boots the React app
- `src/App.js` → defines routes (`/`, `/blog`, `/projects`)
- `src/pages/Main/Main.js` → builds homepage using components
- `src/components/` → contains all UI sections
- `src/data/` → contains all editable content
- `src/contexts/ThemeContext.js` → manages theme state

---

# Key Principle (VERY IMPORTANT)

👉 UI and content are separated.

- Components = structure + layout
- Data files = content

✅ ALWAYS modify content inside `/src/data/`  
❌ DO NOT hardcode content inside components

---

# File Responsibilities

## /src/components/

Reusable UI sections (About, Projects, Navbar, etc.)

Rules:

- Keep components presentational
- Do not embed static content
- Use props or data imports

---

## /src/data/

Source of truth for all content:

- projectsData.js → projects
- skillsData.js → skills
- experienceData.js → experience
- etc.

Rules:

- Update this folder for content changes
- Keep structure consistent
- Do not break existing schema

---

## /src/pages/

Route-level pages:

- Main → homepage
- Blog → blog page
- Project → project details

Rules:

- Compose pages using components
- Avoid heavy logic here

---

## /src/utils/

Helper functions:

- scrolling
- analytics
- image mapping

Rules:

- Keep utilities pure and reusable
- Do not mix UI logic here

---

## /src/theme/ & ThemeContext

Handles theming:

- colors
- images
- dark/light mode

Rules:

- Respect existing theme structure
- Do not hardcode colors in components

---

# Coding Rules

- Use functional components only
- Use React hooks (no class components)
- Keep components small and focused
- Reuse existing components when possible
- Avoid duplication
- Use clear and readable code

Naming:

- Components → PascalCase
- Variables/functions → camelCase

---

# UI & Design Rules

- Maintain clean and modern layout
- Keep spacing and typography consistent
- Ensure full responsiveness (mobile-first)
- Avoid heavy or unnecessary animations
- Use subtle transitions only
- Preserve current design system

---

# Content Rules (CRITICAL)

- Do NOT invent fake projects or experience
- Do NOT hardcode text in components
- Use `/src/data/` for all content updates
- Keep descriptions concise and professional

---

# When Modifying Features

## Adding a new section

1. Create component in `/components/`
2. Add data in `/data/`
3. Import and render in `Main.js`

---

## Updating content

- Only edit `/src/data/*.js`
- Do not touch UI unless required

---

## Adding a new project

- Update `projectsData.js`
- Ensure consistent structure with existing entries

---

## Styling changes

- Follow existing styling approach
- Keep consistency across all components
- Avoid inline styles unless necessary

---

# Performance Rules

- Avoid unnecessary re-renders
- Keep components lightweight
- Optimize images in `/assets/`
- Do not add heavy dependencies

---

# Dependencies

- Do NOT install new packages without approval
- Prefer existing utilities and libraries

---

# Testing Checklist (Before finishing)

- App builds successfully
- No console errors
- Layout works on mobile and desktop
- No broken components or missing data
- Navigation works correctly

---

# Constraints

- Do not modify unrelated files
- Do not restructure the entire project
- Do not change routing unless requested
- Do not break data structure in `/data/`

---

# Preferred Agent Workflow

When making changes:

1. Understand the current structure
2. Identify if change is UI or data
3. Modify the correct layer
4. Keep changes minimal and scoped
5. Maintain consistency with existing patterns

---

# Example Good Behavior

✅ “Add new project” → edit `projectsData.js`  
❌ “Add new project” → hardcode inside component

✅ “Update skills” → edit `skillsData.js`  
❌ “Update skills” → modify UI logic unnecessarily

---

# Goal for Agent

Act like a frontend developer maintaining a production portfolio:

- Clean
- Consistent
- Minimal
- Structured
