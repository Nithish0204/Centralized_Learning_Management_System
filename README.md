# 🎓 LMS Platform

A full-stack **Learning Management System (LMS)** that supports Teacher and Student roles with course management, assignments, submissions, grading, cloud file uploads, email notifications, and live class integration.

Built with a scalable architecture and optimized for **serverless deployment on Vercel**.

---

## 📌 Project Overview

This LMS enables:

* JWT-based authentication (Teacher / Student roles)
* Course creation and enrollment management
* Assignment creation with file attachments
* Student submissions (text + file uploads)
* Inline grading system
* Automatic email notification when graded
* Cloud file storage using Cloudinary
* Live class integration using Agora
* Structured backend logging and request tracing

The project follows a **monorepo structure** with separate frontend and backend services.

---

## 🛠 Tech Stack

### Frontend

* React (SPA)
* React Router
* Axios
* TailwindCSS

### Backend

* Node.js
* Express.js
* Mongoose
* JWT Authentication
* Nodemailer

### Database

* MongoDB Atlas

### File Storage

* Cloudinary (`resource_type: raw`)

### Live Classes

* Agora SDK

### Deployment

* Vercel (Serverless)
* Optional: Render / Railway

---

## 📁 Project Structure

```
Lms/
│
├── backend/
│   ├── api/
│   ├── controllers/
│   ├── models/
│   ├── utils/
│   └── server.js
│
├── frontend/
│   ├── src/
│   └── public/
│
└── vercel.json
```

---

## ⚙️ Installation & Setup

### 1️⃣ Clone the Repository

```bash
git clone <your-repo-url>
cd Lms
```

---

### 2️⃣ Backend Setup

```bash
cd backend
npm install
```

Create a `.env` file inside the `backend/` folder:

```
MONGO_URI=
JWT_SECRET=
FRONTEND_URL=http://localhost:3000

CLOUDINARY_CLOUD_NAME=
CLOUDINARY_API_KEY=
CLOUDINARY_API_SECRET=

SMTP_HOST=
SMTP_PORT=
SMTP_USER=
SMTP_PASS=
EMAIL_FROM=

AGORA_APP_ID=
AGORA_APP_CERTIFICATE=
```

Start the backend server:

```bash
node server.js
```

Backend runs at:

```
http://localhost:5001
```

---

### 3️⃣ Frontend Setup

```bash
cd frontend
npm install
```

Create a `.env` file inside the `frontend/` folder:

```
REACT_APP_API_URL=http://localhost:5001/api
```

Start the frontend:

```bash
npm start
```

Frontend runs at:

```
http://localhost:3000
```

---

## 🚀 Production Deployment

* Configure environment variables in Vercel.
* Set `REACT_APP_API_URL=/api` for serverless deployment.
* Deploy from the root directory (monorepo setup).

---

## 🔐 Security Notes

* Store secrets only in environment variables.
* Use a strong `JWT_SECRET`.
* Restrict CORS to your frontend domain.
* Avoid local file storage in production.
