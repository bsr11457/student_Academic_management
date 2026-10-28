# Student Academic Management System (MERN)

A beginner-friendly Full Stack Development-II project using React, Node.js, Express, MongoDB Atlas, Mongoose, JWT, and bcrypt.

## Features
- Register/login with JWT authentication and hashed passwords
- Student and faculty roles
- Student records: create, list, update, delete
- Attendance records and attendance percentage
- Marks records
- Assignment creation and listing
- React Router, components, props/state, hooks, forms, conditional rendering
- Express routing, middleware, REST APIs, Mongoose CRUD

> Educational starter project. Before production use, add stronger validation, rate limiting, secure deployment settings, audit logs, and tests. The starter stores a JWT in localStorage for ease of learning.

## 1. Requirements
- Node.js LTS and npm
- MongoDB Atlas account (or local MongoDB)
- VS Code or another code editor

## 2. Folder structure
```text
student-academic-management-system/
  backend/
    src/
      config/db.js
      middleware/auth.js
      models/
      routes/
      server.js
    .env.example
    package.json
  frontend/
    src/
      components/
      pages/
      api.js
      App.jsx
      main.jsx
      styles.css
    index.html
    package.json
    vite.config.js
```

## 3. Configure MongoDB
1. Create a free MongoDB Atlas cluster.
2. Create a database user and allow your development IP address.
3. Copy the connection string.
4. In `backend`, copy `.env.example` to `.env`.
5. Put your connection string in `MONGO_URI`. Replace the username, password and database name as appropriate.
6. Set a long random `JWT_SECRET`.

Never commit `.env` or share your database password.

## 4. Start the backend
Open a terminal:
```bash
cd backend
npm install
```
Create `.env` from `.env.example`, then:
```bash
npm run dev
```
The API runs at `http://localhost:5000`. A successful database connection prints a message.

## 5. Start the frontend
Open a second terminal:
```bash
cd frontend
npm install
npm run dev
```
Open the URL printed by Vite, usually `http://localhost:5173`.

## 6. First use
1. Register an account.
2. The registration screen allows `student` or `faculty` role selection for classroom demonstration. In a real application, users must not be allowed to self-assign privileged roles.
3. Log in and use the dashboard.
4. For student management, use a faculty account.
5. Add attendance, marks, and assignments from the relevant forms.

## 7. API overview
- `POST /api/auth/register`, `POST /api/auth/login`, `GET /api/auth/me`
- `GET/POST /api/students`, `PUT/DELETE /api/students/:id`
- `GET/POST /api/attendance`, `GET /api/attendance/student/:studentId`
- `GET/POST /api/marks`, `GET /api/marks/student/:studentId`
- `GET/POST /api/assignments`

All protected endpoints require `Authorization: Bearer <token>`.

## 8. Troubleshooting
- `MongoServerSelectionError`: check `MONGO_URI`, Atlas IP access list, database username/password, and network connection.
- `401 Unauthorized`: log out and log in again; token may have expired.
- `EADDRINUSE`: another process is using port 5000 or 5173; stop it or change the port.
- `npm` cannot find `package.json`: run commands from the correct `backend` or `frontend` folder.
