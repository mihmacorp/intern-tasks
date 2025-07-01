# 🖥️ Task Manager UI – Intern Task

## 🎯 Objective

Your task is to build a **Trello-style web interface** using **Next.js** that consumes the API provided by the [`task-manager-api`](../task-manager-api) project. The application should allow users to sign up, log in, and manage their tasks through a clean, responsive UI.

Use [Trello](https://trello.com/) as a visual reference for styling — but keep the functionality minimal and focused on the following:

---

## ✅ Core Features

### 1. Authentication
Implement user login and signup pages:
- `/signup` – Register a new user
- `/login` – Log in and receive a **JWT token**
- Store JWT in `localStorage` or cookies
- Redirect authenticated users to `/dashboard`
- Logout functionality that clears the token and redirects to `/login`

---

### 2. Dashboard (`/dashboard`)
- Display a welcome message (e.g. "Hi, John 👋")
- Include navigation to "My Tasks"
- Include a logout button

---

### 3. Tasks (`/tasks`)
- Display the list of tasks in a **card-based layout**, similar to a single-column Trello board
- Show:
  - Task title
  - Status (pending/completed)
  - Due date (if present)
- Allow actions:
  - Create new task
  - Edit existing task
  - Delete task

---

### 4. Create Task (`/tasks/new`)
- Form with fields:
  - Title (required)
  - Description (optional)
  - Due date (optional)
  - Status (default: pending)
- Submit to `POST /tasks`

---

### 5. Edit Task (`/tasks/[id]/edit`)
- Fetch task by ID
- Pre-fill the form
- Allow updating task details via `PUT /tasks/{id}`

---

## 🔐 API Integration

Consume the backend API from the [`task-manager-api`](../task-manager-api) project.

- Send the JWT token in the `Authorization: Bearer <token>` header
- Handle 401 errors by redirecting to `/login`
- You may use `axios` or the native `fetch` API

---

## 🛠️ Tech Stack

- **Framework:** Next.js (Pages Router or App Router)
- **Styling:** Tailwind CSS or Chakra UI (your choice)
- **HTTP Client:** Axios (recommended)
- **State:** useState/useEffect or optional useContext for auth

---

## 📁 Suggested Folder Structure

```bash
/pages
├── login.tsx
├── signup.tsx
├── dashboard.tsx
└── tasks/
├── index.tsx
├── new.tsx
└── [id]/
└── edit.tsx

/components
├── TaskCard.tsx
├── TaskForm.tsx
└── Layout.tsx

/utils
├── api.ts # Axios instance with JWT header
└── auth.ts # Auth helpers (e.g., checkToken, logout)
```

---

## 🎁 Bonus (Optional)

- Use modals for creating/editing tasks (like Trello)
- Add loading spinners and toasts for feedback
- Implement status filtering (`/tasks?status=completed`)
- Support mobile responsive layout

---

## 📜 Deliverables

- Functional frontend app connected to the backend
- Code hosted on a public GitHub repo
- `README.md` with:
  - Setup instructions
  - How to run locally
  - How to test endpoints

---

## 🗓️ Deadline

You got 2 weeks to complete this task. Communicate early if you're blocked or need help — this is about learning!

---

## 💡 Learning Outcomes

By completing this task, you will:
- Learn how to integrate frontend apps with real backend APIs
- Understand JWT-based auth workflows in a frontend app
- Practice structuring React/Next.js applications
- Improve your CSS/layout skills using Tailwind or Chakra

---

You’ve got this 💪 — ask for help if you get stuck, and have fun building!
