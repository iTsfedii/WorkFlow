# 🎯 WorkFlow - Team Organization & Management Platform

A full-stack web application designed to manage schedules, tasks, and social networking features for employees and interns within a firm.  Built with security and cybersecurity best practices in mind.

## 📋 Table of Contents

- [Features](#-features)
- [Tech Stack](#-tech-stack)
- [Project Structure](#-project-structure)
- [Security Features](#-security-features)
- [Installation](#-installation)
- [Setup Instructions](#-setup-instructions)
- [API Overview](#-api-overview)
- [Development](#-development)
- [Deployment](#-deployment)
- [Contributing](#-contributing)
- [License](#-license)

---

## ✨ Features

### Core Features
- ✅ **User Authentication** - Secure registration and login with JWT tokens
- ✅ **User Profiles** - Employees/Interns can create and manage profiles with skills and status
- ✅ **Task Management** - Assign, track, and update tasks with priority levels
- ✅ **Calendar & Scheduler** - View and manage shifts, meetings, and deadlines
- ✅ **Dashboard** - Personalized dashboard showing tasks, schedule, and updates
- ✅ **Messaging & Chat** - Direct messaging between team members
- ✅ **Social Feed** - Posts, comments, and social networking features
- ✅ **Admin Panel** - Manage users, tasks, and system settings

### Security Features 🔐
- 🔒 **Password Hashing** - bcryptjs with 10+ salt rounds
- 🔒 **JWT Authentication** - Secure token-based authentication
- 🔒 **2FA Support** - Two-Factor Authentication (TOTP)
- 🔒 **Role-Based Access Control** - Admin, Employee, Intern roles
- 🔒 **Input Validation** - Prevent SQL injection and XSS attacks
- 🔒 **Rate Limiting** - Prevent brute force attacks
- 🔒 **Secure Headers** - CORS, HTTPS enforcement
- 🔒 **Audit Logging** - Track all sensitive actions

---

## 🛠 Tech Stack

### Frontend
- **React. js** - UI library
- **Tailwind CSS / Bootstrap** - Styling
- **React Router** - Client-side routing
- **Axios** - HTTP client for API calls
- **Redux / Context API** - State management
- **React Hook Form** - Form management

### Backend
- **Node.js** - Runtime environment
- **Express.js** - Web framework
- **MongoDB** - NoSQL database
- **Mongoose** - ODM (Object Data Modeling)
- **JWT** - Authentication tokens
- **bcryptjs** - Password hashing
- **Socket.io** - Real-time messaging (optional)

### Additional Tools
- **Docker** - Containerization
- **GitHub Actions** - CI/CD pipeline
- **Postman** - API testing
- **Vercel / Netlify** - Frontend hosting
- **Render / Heroku** - Backend hosting

---

## 📁 Project Structure

workflow/
├── frontend/
│   ├── public/
│   ├── src/
│   │   ├── components/
│   │   │   ├── Auth/
│   │   │   ├── Dashboard/
│   │   │   ├── Tasks/
│   │   │   ├── Calendar/
│   │   │   ├── Messages/
│   │   │   ├── Profile/
│   │   │   ├── Admin/
│   │   │   └── Common/
│   │   ├── pages/
│   │   ├── services/
│   │   ├── hooks/
│   │   ├── context/
│   │   ├── styles/
│   │   ├── App.jsx
│   │   └── main.jsx
│   ├── package.json
│   └── vite.config.js
│
├── backend/
│   ├── src/
│   │   ├── routes/
│   │   │   ├── auth.js
│   │   │   ├── users.js
│   │   │   ├── tasks. js
│   │   │   ├── schedules.js
│   │   │   └── messages.js
│   │   ├── controllers/
│   │   ├── models/
│   │   │   ├── User.js
│   │   │   ├── Task.js
│   │   │   ├── Schedule. js
│   │   │   └── Message.js
│   │   ├── middleware/
│   │   │   ├── auth.js
│   │   │   └── validation.js
│   │   ├── utils/
│   │   ├── config/
│   │   └── app.js
│   ├── . env. example
│   ├── package.json
│   └── server.js
│
├── docs/
│   ├── API.md
│   ├── SECURITY.md
│   └── SETUP.md
│
├── . gitignore
├── .env. example
├── docker-compose.yml
└── README.md

---

## 🔐 Security Features

### Authentication
- **JWT Tokens** - Access & Refresh tokens
- **Password Hashing** - bcryptjs (10+ rounds)
- **2FA/TOTP** - Two-Factor Authentication
- **Secure Cookies** - httpOnly, Secure, SameSite flags

### Authorization
- **Role-Based Access Control (RBAC)**
  - ADMIN: Full system access
  - EMPLOYEE:  Manage interns and own data
  - INTERN: Limited access to own data

### Data Protection
- **Input Validation** - Server-side validation on all endpoints
- **XSS Prevention** - Input sanitization
- **SQL Injection Prevention** - Parameterized queries via Mongoose
- **CORS** - Whitelist allowed domains
- **Rate Limiting** - Prevent brute force attacks (5 attempts per 15 min)

### Monitoring
- **Audit Logging** - Track sensitive actions
- **Error Handling** - Secure error messages (no sensitive info leakage)
- **HTTPS Enforcement** - SSL/TLS in production

---

## 💾 Installation

### Prerequisites
- **Node.js** v16+
- **npm** or **yarn**
- **MongoDB** (local or cloud)
- **Git**

### Clone Repository

git clone https://github.com/iTsfedii/workflow.git
cd workflow

---

## 🚀 Setup Instructions

### Backend Setup

1. Navigate to backend folder:
cd backend

2. Install dependencies:
npm install

3. Create . env file:
cp .env. example .env

4. Configure . env file with your values

5. Start MongoDB (local or cloud)

6. Start backend server:
npm start
# Or for development
npm run dev

Server runs on: http://localhost:5000

---

### Frontend Setup

1. Navigate to frontend folder:
cd frontend

2. Install dependencies:
npm install

3. Create .env file:
cp .env.example .env

4. Configure .env file

5. Start development server:
npm run dev

App runs on: http://localhost:5173

---

## 📡 API Overview

### Authentication Endpoints
POST   /api/auth/register
POST   /api/auth/login
POST   /api/auth/logout
POST   /api/auth/refresh-token
POST   /api/auth/2fa/setup
POST   /api/auth/2fa/verify

### User Endpoints
GET    /api/users/me
GET    /api/users/:id
PUT    /api/users/:id
GET    /api/users (admin only)
DELETE /api/users/:id (admin only)

### Task Endpoints
GET    /api/tasks
POST   /api/tasks
GET    /api/tasks/:id
PUT    /api/tasks/:id
DELETE /api/tasks/:id

### Schedule Endpoints
GET    /api/schedules
POST   /api/schedules
GET    /api/schedules/: id
PUT    /api/schedules/:id
DELETE /api/schedules/:id

### Message Endpoints
GET    /api/messages
POST   /api/messages
GET    /api/messages/:conversationId
PUT    /api/messages/:id/read

For detailed API documentation, see API.md

---

## 👨‍💻 Development

### Project Phases

**Phase 1: Foundation**
- User authentication
- JWT implementation
- Database models

**Phase 2: Core Features**
- Task management
- Calendar/Scheduler
- User profiles

**Phase 3: Social Features**
- Direct messaging
- Social feed
- Notifications

**Phase 4: Security Hardening**
- 2FA implementation
- Audit logging
- Rate limiting

**Phase 5: Testing & Polish**
- Unit tests
- Integration tests

**Phase 6: Deployment**
- Docker setup
- Production deployment

---

## 🌐 Deployment

### Frontend (Vercel/Netlify)
1. Push code to GitHub
2. Connect repository to Vercel/Netlify
3. Set environment variables
4. Deploy! 

### Backend (Render/Heroku)
1. Push code to GitHub
2. Connect repository to Render/Heroku
3. Set environment variables
4. Deploy! 

---

## 🤝 Contributing

1. Create a feature branch
2. Make your changes
3. Commit with meaningful messages
4. Push to branch
5. Open a Pull Request

---

## 📝 License

This project is licensed under the MIT License.

---

## 👤 Author

**iTsfedii**
- GitHub: [@iTsfedii](https://github.com/iTsfedii)

---

**Happy coding! 🚀**
