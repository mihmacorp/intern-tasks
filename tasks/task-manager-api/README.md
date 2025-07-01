# 🧠 Intern Backend Task – FastAPI Task Manager (Trello-style)


Your mission is to build a **FastAPI backend** that powers a simple **Trello-style Task Manager** app.

This backend will allow users to:
- Sign up and log in
- Get a JWT token
- Manage their own tasks (create, edit, view, delete)

This API will be consumed by a frontend built with Next.js that looks and feels like Trello — but much simpler.

---

## 🧱 What You’ll Build

You'll create a REST API with the following core features:

### 1. 👤 User Authentication

- `POST /signup` – Register a new user (store hashed password)
- `POST /login` – Log in and receive a JWT token
- `GET /me` – Get the current logged-in user's details

✅ **Things to handle:**
- Use `passlib` to hash passwords securely
- Use `python-jose` or `PyJWT` to create and validate JWT tokens
- Protect all task routes with JWT (only logged-in users can use them)

---

### 2. ✅ Task Management (CRUD)

- `GET /tasks` – List all tasks for the logged-in user
- `POST /tasks` – Create a new task
- `GET /tasks/{task_id}` – View a single task
- `PUT /tasks/{task_id}` – Update a task
- `DELETE /tasks/{task_id}` – Delete a task

✅ Each task should have the following fields:
- `id` (int)
- `title` (str)
- `description` (optional, str)
- `status` (default: "pending" | can also be "completed")
- `due_date` (optional, date)
- `owner_id` (linked to user)

Tasks must belong to a user. A user **cannot see or edit another user’s tasks**.

---

## 📦 Tech Stack

Use the following tools/libraries:

- `fastapi`
- `uvicorn`
- `sqlalchemy` (or `tortoise-orm` if you're comfortable with async)
- `passlib[bcrypt]` – for password hashing
- `python-jose` or `PyJWT` – for JWT
- `pydantic` – for request/response validation
- `sqlite` for the database (PostgreSQL optional)

---

## 🔐 Auth Notes

- JWT tokens should be returned on login and passed via the `Authorization: Bearer <token>` header.
- All task routes must be protected using FastAPI dependencies.

---

## 🧩 Project Structure Suggestion

```bash
app/
├── main.py
├── models.py
├── schemas.py
├── auth.py
├── database.py
├── crud.py
└── routes/
    ├── users.py
    └── tasks.py
```

Use routers to keep things modular. Each route file (`users.py`, `tasks.py`) should register its own endpoints.

## 📜 Deliverables

* Working FastAPI backend
* All endpoints functional and tested
* GitHub repository with:
   * Clear folder structure
   * `requirements.txt`
   * `README.md` with setup instructions
* Optional: use Swagger UI to demo endpoints

## 🗓️ Deadline

This task is going for 2 weeks – but keep me updated on your progress and ask questions if you're stuck.

## 💡 Bonus (Optional)

If you finish early or want to stretch yourself:

* Add filtering (`/tasks?status=completed`)
* Add pagination
* Add a "priority" field to tasks
* Allow editing user profile info (`PUT /me`)
* Add simple rate-limiting to protect endpoints

## 🧠 What You'll Learn

* Building real-world REST APIs
* Structuring FastAPI projects
* JWT-based user auth
* Data modeling with SQLAlchemy or Tortoise
* Pydantic validation
* Writing secure, clean, and maintainable backend code

Let me know once your GitHub repo is ready!

