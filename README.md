# 🎓 Academic Project Portal

A full-stack **Academic Project Management Portal** designed to streamline the final-year project workflow for students, mentors, and administrators. The platform provides a centralized system for team formation, mentor assignment, project management, approvals, document submissions, deadlines, and academic project tracking.

The application is built with a **React frontend** and a **Node.js/Express backend**, with **PostgreSQL** used for persistent data storage.

---

## 🚀 Features

### 👨‍🎓 Student Portal

* Student registration and authentication
* Student dashboard
* Profile management
* Team formation
* Student invitations and requests
* Mentor selection
* Project creation and management
* Project progress tracking
* Report and document submissions
* Project approval workflow
* Academic project information

### 👨‍🏫 Mentor Portal

* Mentor authentication
* Mentor dashboard
* View assigned student teams
* Review student projects
* Project approval
* Report/review approval workflow
* Monitor project progress
* Manage assigned projects

### 🛠️ Admin Portal

* Dedicated administrator authentication
* Student management
* Mentor management
* Project monitoring
* Announcement management
* Project deadline management
* Academic project administration

---

## 🏗️ System Architecture

```text
                    Academic Project Portal
                              │
                 ┌────────────┴────────────┐
                 │                         │
          React Frontend             Node.js Backend
        project-portal-main      project-portal-Backend-main
                 │                         │
                 │       REST APIs         │
                 └────────────┬────────────┘
                              │
                              ▼
                    PostgreSQL / Neon
```

### Application Flow

```text
Student / Mentor / Admin
          │
          ▼
    React Frontend
          │
          │ Axios / REST API
          ▼
   Express.js Backend
          │
          ▼
     Controllers
          │
          ▼
   Sequelize Models
          │
          ▼
 PostgreSQL / Neon Database
```

---

## 🛠️ Tech Stack

### Frontend

| Technology                 | Purpose                 |
| -------------------------- | ----------------------- |
| React 18                   | User interface          |
| React Router               | Client-side routing     |
| Axios                      | API communication       |
| Tailwind CSS               | UI styling              |
| React Query                | Server-state management |
| Framer Motion              | Animations              |
| React Icons / Lucide       | Icons                   |
| ECharts                    | Data visualization      |
| JWT Decode                 | JWT handling            |
| React Toastify / Hot Toast | Notifications           |

### Backend

| Technology | Purpose                    |
| ---------- | -------------------------- |
| Node.js    | Backend runtime            |
| Express.js | REST API framework         |
| PostgreSQL | Database                   |
| Neon       | Serverless PostgreSQL      |
| Sequelize  | ORM                        |
| JWT        | Authentication             |
| bcrypt     | Password hashing           |
| Multer     | File uploads               |
| Nodemailer | Email functionality        |
| dotenv     | Environment configuration  |
| CORS       | Cross-origin communication |

---

## 📁 Repository Structure

```text
Academic-Project-Portal/
│
├── project-portal-main/              # React Frontend
│   ├── public/
│   ├── src/
│   │   ├── admin/
│   │   ├── mentor/
│   │   ├── student/
│   │   ├── App.js
│   │   ├── LandingPage.tsx
│   │   └── ...
│   ├── package.json
│   ├── tailwind.config.js
│   └── README.md
│
├── project-portal-Backend-main/      # Node.js Backend
│   ├── config/
│   ├── controllers/
│   ├── middleware/
│   ├── migrations/
│   ├── models/
│   ├── routes/
│   ├── utils/
│   ├── uploads/
│   ├── server.js
│   ├── package.json
│   └── README.md
│
└── README.md                         # Main project documentation
```

---

## ⚙️ Getting Started

### Prerequisites

Make sure you have the following installed:

* [Node.js](https://nodejs.org/)
* npm
* Git
* PostgreSQL database or Neon PostgreSQL account

---

## 1. Clone the Repository

```bash
git clone https://github.com/Edwinsanthosh/Academic-Project-Portal.git
```

Navigate into the project:

```bash
cd Academic-Project-Portal
```

---

## 2. Setup the Backend

```bash
cd project-portal-Backend-main
```

Install dependencies:

```bash
npm install
```

Create a `.env` file:

```env
PORT=5000
DATABASE_URL=your_postgresql_connection_string
JWT_SECRET=your_jwt_secret
```

Start the backend:

```bash
npm start
```

The backend will run using the configured port.

---

## 3. Setup the Frontend

Open another terminal and navigate to:

```bash
cd project-portal-main
```

Install dependencies:

```bash
npm install
```

Create/configure the frontend `.env` file:

```env
REACT_APP_API_URL=http://localhost:5000
```

Start the React application:

```bash
npm start
```

The frontend will be available at:

```text
http://localhost:3000
```

---

## 🔐 Authentication

The application uses **JWT-based authentication** for protected operations.

```text
Login
  │
  ▼
Backend validates credentials
  │
  ▼
JWT generated
  │
  ▼
Frontend stores authentication state
  │
  ▼
JWT sent with protected API requests
```

Passwords are securely hashed before being stored in the database.

---

## 📊 Database

The backend uses **PostgreSQL** with Sequelize ORM.

The application contains models for areas including:

* Students
* Mentors
* Administrators
* Teams
* Projects
* Invitations
* Announcements
* Project deadlines
* Document formats
* Professional training
* Final-year projects

---

## 🔄 Project Workflow

```text
Student Registration
        │
        ▼
   Create / Join Team
        │
        ▼
   Select Mentor
        │
        ▼
   Mentor Approval
        │
        ▼
   Create Project
        │
        ▼
 Project Development
        │
        ▼
 Submit Reports / Documents
        │
        ▼
   Mentor Reviews
        │
        ▼
     Approval
        │
        ▼
 Final Project Completion
```

---

## 📂 Project Components

### Frontend

The frontend is organized around the three major user roles:

```text
student/
mentor/
admin/
```

Each role contains its own pages, components, and API integration, allowing the application to maintain a clear separation between user-specific functionality.

### Backend

The backend follows a modular architecture:

```text
routes
   ↓
controllers
   ↓
models
   ↓
database
```

This separation keeps API routing, application logic, and database operations organized and maintainable.

---

## 🔌 Frontend–Backend Communication

The React frontend communicates with the Express backend using REST APIs.

```text
React
  │
  │ Axios
  ▼
Express REST API
  │
  ▼
Controllers
  │
  ▼
Sequelize
  │
  ▼
PostgreSQL
```

The frontend API URL is configured through:

```env
REACT_APP_API_URL=...
```

---

## 📌 Environment Variables

Do not commit sensitive environment variables to the repository.

Typical backend configuration:

```env
PORT=5000
DATABASE_URL=your_database_url
JWT_SECRET=your_secret
```

Frontend configuration:

```env
REACT_APP_API_URL=http://localhost:5000
```

Use your own production values when deploying the application.

---

## 🧪 Frontend Commands

Inside `project-portal-main`:

```bash
npm start
```

Run development server.

```bash
npm test
```

Run tests.

```bash
npm run build
```

Create a production build.

---

## 🖥️ Backend Commands

Inside `project-portal-Backend-main`:

```bash
npm install
```

Install dependencies.

```bash
npm start
```

Start the backend server.

---

## 🔒 Security

The application includes several security-related mechanisms:

* JWT-based authentication
* Password hashing with bcrypt
* Environment-based configuration
* Protected API operations
* CORS configuration
* Server-side validation
* Controlled file uploads

> Never expose database credentials, JWT secrets, email credentials, or other sensitive configuration in the repository.

---

## 🎯 Project Objective

The main objective of the Academic Project Portal is to replace fragmented final-year project management processes with a centralized digital workflow.

Instead of managing teams, mentors, approvals, reports, and project information through separate communication channels, the platform brings these activities into a single application.

---

## 👨‍💻 Author

**Edwin Santhosh**

GitHub: [Edwinsanthosh](https://github.com/Edwinsanthosh)

---

## 📄 License

This project is developed as an academic/project portfolio application.
