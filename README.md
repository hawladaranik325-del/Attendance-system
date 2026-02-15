# Attendance-system

# 📌 College Attendance Management System

A full-stack web application for managing and monitoring college student attendance using secure authentication and TOTP-based verification.

---

## 🚀 Project Overview

This system allows:

- Teachers to authenticate securely
- Students to mark attendance using Google Authenticator (TOTP)
- Admin to monitor student attendance percentage
- Automatic eligibility calculation (75% rule)

The system is built using:

- **Frontend:** React (Vite)
- **Backend:** Node.js + Express
- **Database:** MongoDB Atlas
- **Authentication:** JWT + TOTP (Speakeasy)

---

## 🏗️ Tech Stack

### Backend
- Node.js
- Express.js
- MongoDB (Mongoose)
- JWT (jsonwebtoken)
- bcrypt
- Speakeasy (TOTP)
- dotenv

### Frontend
- React
- Vite
- Fetch API

---

## 🔐 Features

### 👨‍🏫 Teacher
- Secure login using JWT
- Generates unique Teacher ID
- Password hashing with bcrypt

### 👨‍🎓 Student
- Marks attendance using Google Authenticator code
- Attendance stored securely in database
- Duplicate attendance prevention (per day)

### 👨‍💼 Admin
- View all students
- View attendance percentage
- View eligibility status
- 75% attendance rule enforcement

---

## 📊 Attendance Logic

- Total academic days assumed: **90**
- Attendance Percentage Formula:

```
Percentage = (Present Days / Total Days) × 100
```

- Eligibility Criteria:

```
>= 75% → Eligible
< 75% → Not Eligible
```

---

## 📁 Project Structure

```
attendance-system/
│
├── models/
│   ├── Student.js
│   ├── Teacher.js
│
├── routes/
│   ├── admin.js
│   ├── student.js
│   ├── teacher.js
│
├── middleware/
│   ├── authAdmin.js
│   ├── authTeacher.js
│
├── server.js
├── package.json
│
├── attendance-frontend/
│   ├── src/
│   ├── package.json
│   └── vite.config.js
│
└── README.md
```

---

## ⚙️ Installation & Setup

### 1️⃣ Clone the Repository

```bash
git clone <your-repo-url>
cd attendance-system
```

---

### 2️⃣ Backend Setup

```bash
npm install
```

Create a `.env` file:

```
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_secret_key
PORT=5000
```

Run backend:

```bash
npm run dev
```

Backend runs on:

```
http://localhost:5000
```

---

### 3️⃣ Frontend Setup

```bash
cd attendance-frontend
npm install
npm run dev
```

Frontend runs on:

```
http://localhost:5173
```

---

## 🔄 API Endpoints

### Teacher
- `POST /api/teacher/register`
- `POST /api/teacher/login`

### Student
- `POST /api/student/create`
- `POST /api/student/mark-attendance`

### Admin
- `GET /api/admin/percentage/all`
- `GET /api/admin/percentage/:studentId`

---

## 🔑 Authentication Flow

1. Teacher logs in → receives JWT
2. JWT used in Authorization header:
   ```
   Authorization: Bearer <token>
   ```
3. Admin routes protected via middleware
4. Student attendance verified via TOTP

---

## 🛡️ Security Features

- Password hashing (bcrypt)
- JWT authentication
- TOTP verification
- Duplicate attendance prevention
- Protected admin routes

---

## 🎯 Use Case

This system can be used in:

- Colleges
- Training institutes
- Academic projects
- Attendance tracking systems

---

## 📌 Future Improvements

- Role-based dashboard UI
- CSV export
- Graphical attendance charts
- Multi-semester support
- Class-wise filtering
- Production deployment

---

## 👨‍💻 Developed By

**Shubham**  
Diploma in Computer Science & Technology  
2026
