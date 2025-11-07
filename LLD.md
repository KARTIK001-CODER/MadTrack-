# 🧠 **Low-Level Design (LLD) — Productivity Tracker (Phase 1)**

---

## 🎯 **Objective**

A personal productivity tracking system that allows Kartik and his brother to manage tasks, maintain daily reports, and monitor progress — helping both stay consistent and accountable.

---

## 🏗️ **System Overview**

The system enables users to:

* Create accounts and securely log in.
* Manage daily tasks (add, update, delete, complete).
* Write daily reports summarizing their day.
* View productivity insights via a dashboard.
* Share daily progress with another user.

---

## ⚙️ **Core Functional Modules**

---

### **1. Authentication Module**

**Purpose:**
Handle secure login, registration, and session management.

**Functions:**

* `registerUser()` — Creates a new user account.
* `loginUser()` — Authenticates user credentials and starts a session.
* `logoutUser()` — Logs out the current user.
* `authMiddleware()` — Protects routes to ensure only logged-in users can access internal pages.

**Future Enhancements:**

* JWT or cookie-based authentication.
* Multi-user support with roles (e.g., admin, standard user).

---

### **2. Task Management Module**

**Purpose:**
Allow users to create, modify, and track daily tasks.

**Functions:**

* `addTask(taskTitle, description, dueDate, priority)` — Adds a new task.
* `editTask(taskId, updatedDetails)` — Updates an existing task.
* `deleteTask(taskId)` — Deletes a specific task.
* `markTaskAsDone(taskId)` — Marks a task as completed.
* `getAllTasks(userId)` — Fetches all tasks for the user.
* `filterTasksByDate()` / `filterTasksByStatus()` — Filters tasks for better organization.

**Future Enhancements:**

* Task reminders and recurring tasks.
* Tagging or categorization (e.g., “Work”, “Personal”).

---

### **3. Daily Report Module**

**Purpose:**
Provide a structured way to log daily activities and achievements.

**Functions:**

* `createReport(date, summary, completedTasks)` — Creates a daily summary.
* `editReport(reportId, updatedText)` — Edits an existing report.
* `getReportByDate(date)` — Retrieves a report for a specific day.
* `listAllReports(userId)` — Displays all reports chronologically.

**Future Enhancements:**

* Mood tracking or focus levels.
* Rich text editor support (Markdown, emojis).
* Share report option with your brother.

---

### **4. Progress Dashboard Module**

**Purpose:**
Show visual insights into user productivity and consistency.

**Functions:**

* `getTaskStats(userId)` — Returns total, completed, and pending tasks.
* `getDailyReportSummary(userId)` — Provides weekly completion summaries.
* `getWeeklyOverview()` — Displays a chart of productivity trends.
* `getStreakCount()` — Calculates consecutive active days.

**Future Enhancements:**

* Productivity heatmaps.
* Weekly/monthly comparisons.
* Gamified badges for milestones.

---

### **5. Sharing & Collaboration Module**

**Purpose:**
Enable users (like Kartik and his brother) to share progress and feedback.

**Functions:**

* `shareReportWithUser(reportId, targetUserId)` — Shares a report with another user.
* `getSharedReports()` — Displays reports shared by others.
* `addCommentToReport(reportId, commentText)` — Allows feedback and motivation.

**Future Enhancements:**

* Notification system (e.g., “Your brother completed 5 tasks today”).
* Shared team goals or productivity challenges.

---

### **6. User Profile Module**

**Purpose:**
Manage personal settings, preferences, and appearance.

**Functions:**

* `updateProfileInfo(name, avatar, preferences)` — Update user information.
* `getProfileDetails()` — Fetch user profile data for display.
* `setThemeMode(theme)` — Switch between light and dark themes.

**Future Enhancements:**

* Productivity badges.
* Profile analytics (total tasks completed, streak records).

---

## 🧩 **Data Flow (High-Level Overview)**

```
User → Authentication → Dashboard
     → Task Management → Dashboard
     → Daily Report → Report Timeline
     → Sharing Module → Brother’s Dashboard
```

**Example Flow:**

1. User logs in.
2. Adds today’s tasks.
3. Completes some tasks.
4. Writes a daily report summarizing work.
5. Shares it with brother for review.
6. Dashboard updates with progress metrics.

---

## 🖥️ **Frontend Structure (Pages & Components)**

| **Page**                | **Description**                   | **Key Components**                 |
| ----------------------- | --------------------------------- | ---------------------------------- |
| **Login / Signup**      | Handles user authentication       | Form, validation, redirect         |
| **Dashboard**           | Displays productivity overview    | Stats cards, charts, streaks       |
| **Tasks Page**          | Create and manage tasks           | Task form, filters, status toggles |
| **Daily Report Page**   | Write and view daily summaries    | Text editor, history view          |
| **Shared Reports Page** | View shared reports between users | Report cards, comments             |
| **Profile Page**        | Manage profile & preferences      | Avatar, theme, name                |
| **Settings Page**       | Account and privacy options       | Logout, data reset, preferences    |

---

## 🧭 **Future Add-ons (Phase 2 / 3)**

* Real-time updates via WebSockets.
* Mobile app support (React Native).
* Analytics dashboard with trends.
* Google Calendar / Notion integration.
* Export daily reports as PDF summaries.

---
