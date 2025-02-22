### Full-Stack Task Management App - `README.md`


---

## README.md
```md
# Task Management App (Full Stack)

A Task Management application built using:
- Frontend: React + TypeScript
- Backend: Node.js (Express) + TypeScript
- Database: PostgreSQL

---

## Features
- User Authentication (Register, Login, Logout)
- Task CRUD Operations (Create, Update, Delete, Mark Complete)
- Secure API with JWT Authentication
- PostgreSQL Database with Prisma ORM
- Environment Variables for Configuration

---

## Prerequisites

Required Software:
- Node.js (LTS) - https://nodejs.org/
- PostgreSQL - https://www.postgresql.org/
- npm (comes with Node.js)

---

# Backend Setup (Node.js + Express)

## 1. Clone the Repository
```sh
git clone https://github.com/Tishyaketu/lumaa-spring-2025-swe
cd fullstack-task-manager/backend
```

## 2. Install Backend Dependencies
```sh
npm install
```

## 3. Set Up Environment Variables
Create a `.env` file in the `backend/` directory:
```sh
PORT=5000
DATABASE_URL=postgresql://youruser:yourpassword@localhost:5432/taskmanager
JWT_SECRET=your_secret_key
```
Replace `youruser`, `yourpassword`, and `taskmanager` with your actual PostgreSQL database credentials.  
Use a strong `JWT_SECRET` for authentication security.

---

## 4. Database Setup (Migrations)
Ensure PostgreSQL is running and execute:
```sh
npx prisma migrate dev --name init
```
This will create the required tables in the PostgreSQL database.

---

## 5. Run the Backend Server
Start the backend server using:
```sh
npm run dev
```
- The API runs on `http://localhost:5000`
- Press `CTRL+C` to stop the server.

---

# Frontend Setup (React + TypeScript)

## 1. Clone the Repository & Navigate to Frontend
```sh
cd ../frontend
```

## 2. Install Frontend Dependencies
```sh
npm install
```

## 3. Set Up Environment Variables
Create a `.env` file in the `frontend/` directory:
```sh
REACT_APP_API_URL=http://localhost:5000
```
Replace the API URL if the backend is deployed on a different server.

---

## 4. Run the Frontend
Start the React app using:
```sh
npm start
```
- The frontend runs on `http://localhost:3000`
- Press `CTRL+C` to stop the React server.

---

# API Testing (Postman / cURL)

## 1. Register a User
```sh
curl -X POST http://localhost:5000/auth/register \
-H "Content-Type: application/json" \
-d '{"username": "testuser", "password": "password123",  "confirmPassword": "password123"}'
```

## 2. Login a User
```sh
curl -X POST http://localhost:5000/auth/login \
-H "Content-Type: application/json" \
-d '{"username": "testuser", "password": "password123"}'
```
This returns a JWT token, which should be included in requests to protected routes.

## 3. Get Tasks (Authenticated)
```sh
curl -X GET http://localhost:5000/tasks \
-H "Authorization: Bearer YOUR_JWT_TOKEN"
```

## 4. Create a Task
```sh
curl -X POST http://localhost:5000/tasks \
-H "Authorization: Bearer YOUR_JWT_TOKEN" \
-H "Content-Type: application/json" \
-d '{"title": "New Task", "description": "Description of the task"}'
```

---

# Notes on Testing
1. Ensure the backend is running (`npm run dev`) before testing APIs.
2. Use Postman, cURL, or React frontend for testing API endpoints.
3. Check `http://localhost:5000/tasks` (backend) and `http://localhost:3000` (frontend) for correct server response.
4. Restart the frontend if `.env` changes (`npm start` again).
5. For database issues, rerun migrations:
   ```sh
   npx prisma migrate dev --name init
   ```

---
# Salary Expectations per month:
## My salary expectations per month are $1600 to $2400
