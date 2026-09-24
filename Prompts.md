# AI Architectural Queries & Prompt Engineering Log ("Prompts.md")

This log documents the iterative prompt engineering, architectural consultations, and design queries used to create the Product Requirements Document (PRD), State Management Architecture, and UI/UX layout for **TaskMatrix**.

## 1. Project Selection & Scope Assessment
**Query:**
> "Evaluate three capstone project ideas (LMS, Healthcare EHR, Agile Task Board Jira clone) for a Frontend Specialist track. Which choice offers the highest visual impact, best state management evaluation for hiring managers, and avoids backend bottlenecks?"

**Output & Decision:**
> Selected **TaskMatrix (Agile Project Management System)** due to high visual appeal of Drag-and-Drop Kanban boards, rich frontend state requirements (Zustand/Redux), clear layout hierarchy, and instant relevance to software engineering hiring managers.

---

## 2. Tech Stack Optimization & State Architecture
**Query:**
> "Design a clean, scalable Zustand global state tree for a Next.js 14 App Router drag-and-drop Kanban application. How should tasks, columns, filters, and UI modals be separated to prevent unnecessary re-renders?"

**Output & Decision:**
> Structured state into 4 decoupled sub-stores (`AuthStore`, `BoardStore`, `FilterStore`, `UIStore`). `BoardStore` handles array normalization (`Record<TaskId, Task>`) for O(1) updates during drag-and-drop operations.

---

## 3. Mock API Payload Structure
**Query:**
> "Define RESTful Mock API payloads for a client-heavy Kanban application using JSON / MSW syntax that can later be seamlessly connected to a Supabase or Express backend."

**Output & Decision:**
> Created standardized schemas for `/api/v1/board`, `/api/v1/tasks`, and `/api/v1/activity` with full type safety in TypeScript.

---

## 4. UI/UX & Responsive Layout Strategy
**Query:**
> "What are the modern UX best practices for responsive Kanban boards when transitioning from desktop (1440px) to mobile (375px) viewports?"

**Output & Decision:**
> Implemented horizontal scroll snapping for columns on mobile, drawer-based filter triggers, and floating quick-add task action button (FAB) for touch devices.
