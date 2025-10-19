````markdown
# 📝 Notes App

A **full-stack MERN Notes Application** that allows users to register, log in, create, update, delete, and search notes securely.  
Built with **React.js**, **Express.js**, **MongoDB**, and **JWT authentication**.

---

## 🚀 Features

### 🌐 Frontend (React)

- Secure authentication and session handling
- Create, edit, and delete notes
- Search functionality by title or description
- Responsive UI built with Tailwind CSS

### ⚙️ Backend (Express + MongoDB)

- RESTful API with JWT-based authentication
- CRUD operations for notes
- Encrypted passwords with bcrypt
- Protected routes using middleware

---

## 🧩 Tech Stack

| Layer          | Technology                                  |
| -------------- | ------------------------------------------- |
| Frontend       | React.js, React Router, Axios, Tailwind CSS |
| Backend        | Node.js, Express.js                         |
| Database       | MongoDB (Mongoose ORM)                      |
| Authentication | JWT (JSON Web Token)                        |
| Security       | bcrypt.js, dotenv                           |

## ⚙️ Setup Instructions

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/<your-username>/notes-app.git
cd notes-app
```
````

### 2️⃣ Install Dependencies

#### Backend

```bash
cd backend
npm install
```

#### Frontend

```bash
cd ../frontend
npm install
```

---

## 🔑 Environment Variables

Create a `.env` file in the backend root:

```
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret_key
NODE_ENV=development
PORT=5000
```

---

## 🗄️ Backend Scripts

### Start the Backend

```bash
npm run server
```

### Example `server.js` Start Log

```
Server started at port 5000
MongoDB connected
```

---

## 🧠 API Endpoints

| Method | Endpoint              | Description             | Auth |
| ------ | --------------------- | ----------------------- | ---- |
| POST   | `/api/users/register` | Register new user       | ❌   |
| POST   | `/api/users/login`    | Log in user             | ❌   |
| GET    | `/api/users/me`       | Get logged-in user info | ✅   |
| GET    | `/api/notes`          | Fetch all notes         | ✅   |
| POST   | `/api/notes`          | Create a new note       | ✅   |
| PUT    | `/api/notes/:id`      | Update a note           | ✅   |
| DELETE | `/api/notes/:id`      | Delete a note           | ✅   |

---

## 💻 Frontend Setup

### 1. Connect API URL

In `frontend/src/App.jsx` or `axios` configuration:

```js
axios.defaults.baseURL = "http://localhost:5000";
```

### 2. Run the Frontend

```bash
npm run dev
```

or (for Create React App)

```bash
npm start
```

---

## 🔐 Authentication Flow

1. User registers → `POST /api/users/register` → receives JWT token.
2. Token stored in `localStorage`.
3. On every API call, frontend sends token in headers:

   ```
   Authorization: Bearer <token>
   ```

4. Backend validates token using middleware (`protect`).

---

## 🧰 Middleware – protect.js

- Verifies JWT token from headers.
- Fetches user from database (excluding password).
- Attaches user object to `req.user`.
- Returns 401 if invalid or missing token.

---

## 🧠 Database Models

### User Model

- Fields: `username`, `email`, `password`
- Password encrypted with bcrypt
- Method: `matchPassword` for login validation

### Note Model

- Fields: `title`, `description`, `createdBy`
- Linked with User via ObjectId

---

## 🧑‍💻 Author

**Arsha Vardhan**
CSE Student @ KL University
Focused on full-stack web development and UI/UX design.

---

## 📜 License

This project is licensed under the **MIT License**.

---

## ⚡ Quick Start Summary

```bash
# Clone project
git clone https://github.com/<your-username>/notes-app.git

# Setup backend
cd backend
npm install
npm run server

# Setup frontend
cd ../frontend
npm install
npm start
```

Then open **[http://localhost:3000](http://localhost:3000)** (React)
API runs on **[http://localhost:5000](http://localhost:5000)**

```


```
