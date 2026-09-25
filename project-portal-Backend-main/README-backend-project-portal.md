# Academic Project Portal — Backend

Backend API for the Academic Project Portal, a system designed to manage the final-year project workflow between students, mentors, and administrators.

## Overview

The backend provides REST APIs for authentication, student and mentor management, team formation, project management, approvals, administrative operations, document uploads, and academic project tracking.

It is built using **Node.js and Express.js** with **Sequelize** for database interaction and PostgreSQL/Neon support.

## Tech Stack

- **Node.js**
- **Express.js**
- **PostgreSQL**
- **Neon Serverless PostgreSQL**
- **Sequelize ORM**
- **JWT**
- **bcrypt / bcryptjs**
- **Multer**
- **Nodemailer**
- **CORS**
- **dotenv**
- **xlsx**
- **Sharp**
- **adm-zip / unzipper**

## Core Features

### Authentication

- Student authentication
- Mentor authentication
- Admin authentication
- JWT-based authentication
- Password hashing using bcrypt

### Student Management

- Student registration and login
- Student profile management
- Student project information
- Student/team relationship management

### Team Management

- Team creation and management
- Team member invitations
- Team-related requests
- Team and project relationship handling
- Workflow validation to prevent invalid project participation

### Mentor Management

- Mentor information management
- Mentor assignment workflow
- Mentor-side project/team access
- Project approval operations
- Report/review workflow

### Project Management

- Create and manage academic projects
- Project status tracking
- Project approval workflow
- Report/document submission
- Final-year project management
- Project deadlines and related academic data

### Administration

- Administrative authentication
- Student and mentor management
- Project monitoring
- Announcements
- Academic project administration
- Administrative workflow operations

### File Handling

The backend supports file uploads using **Multer** and maintains an `uploads/` directory for uploaded project-related files.

## Backend Structure

```text
project-portal-Backend-main/
├── config/
├── controllers/
│   ├── adminControllers.js
│   ├── mentorControllers.js
│   ├── projectControllers.js
│   ├── studentControllers.js
│   └── teamControllers.js
│
├── middleware/
├── migrations/
│
├── models/
│   ├── admin.js
│   ├── announcement.js
│   ├── documentformats.js
│   ├── finalYearProject.js
│   ├── invitations.js
│   ├── mentor.js
│   ├── professionalTraining1.js
│   ├── professionalTraining2.js
│   ├── projectdeadlines.js
│   ├── student.js
│   └── team.js
│
├── routes/
│   ├── admin.js
│   ├── auth.js
│   ├── mentors.js
│   ├── projectRoutes.js
│   ├── students.js
│   └── teamRoutes.js
│
├── utils/
├── uploads/
├── server.js
├── package.json
└── README.md
```

## API Organization

The API is separated into route modules based on responsibility:

| Route Module | Responsibility |
|---|---|
| `auth.js` | Authentication-related operations |
| `students.js` | Student operations |
| `mentors.js` | Mentor operations |
| `teamRoutes.js` | Team and invitation operations |
| `projectRoutes.js` | Project-related operations |
| `admin.js` | Administrative operations |

Controllers contain the application logic for these operations, while Sequelize models represent the database entities and their relationships.

## Database

The backend uses **PostgreSQL** with **Sequelize ORM**.

The data model includes entities for:

- Students
- Mentors
- Admins
- Teams
- Projects
- Invitations
- Announcements
- Project deadlines
- Document formats
- Professional training
- Final-year projects

Database configuration is loaded through environment variables.

## Getting Started

### Prerequisites

Install:

- Node.js
- npm
- PostgreSQL database or Neon PostgreSQL
- Git

### Installation

Clone the repository:

```bash
git clone https://github.com/Edwinsanthosh/Academic-Project-Portal.git
```

Navigate to the backend:

```bash
cd Academic-Project-Portal/project-portal-Backend-main
```

Install dependencies:

```bash
npm install
```

### Environment Variables

Create a `.env` file in the backend root.

Use your own database and authentication configuration. For example:

```env
PORT=5000
DATABASE_URL=your_postgresql_connection_string
JWT_SECRET=your_jwt_secret
```

Add any additional variables required by your local configuration.

> Never commit real database credentials, JWT secrets, email credentials, or other sensitive values to GitHub.

### Run the Backend

```bash
npm start
```

The server will start using the configuration defined in `.env`.

## Backend Architecture

The backend follows a modular API structure:

```text
Client / React Frontend
          │
          ▼
       Express
          │
     ┌────┴────┐
     ▼         ▼
   Routes   Middleware
     │
     ▼
 Controllers
     │
     ▼
 Sequelize Models
     │
     ▼
 PostgreSQL / Neon
```

## Frontend Repository

The React frontend is located in:

```text
project-portal-main
```

It communicates with this backend through REST APIs.

## Development Workflow

1. Start the PostgreSQL/Neon database.
2. Configure backend environment variables.
3. Start the backend server.
4. Configure the frontend API URL.
5. Start the React frontend.
6. Use the appropriate student, mentor, or admin interface.

## Security Considerations

- Passwords are hashed before storage.
- JWT is used for authenticated sessions.
- CORS is configured for frontend/backend communication.
- Environment variables are used for sensitive configuration.
- File uploads are handled through Multer.

## Author

**Edwin Santhosh**

GitHub: https://github.com/Edwinsanthosh
