<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=12,20,24&height=200&section=header&text=PEC%20Innovation%20Hub&fontSize=40&fontColor=fff&animation=twinkling&fontAlignY=35&desc=Where%20Student%20Projects%20Come%20Alive&descAlignY=58&descAlign=50" width="100%"/>

[![GitHub Stars](https://img.shields.io/github/stars/jeswinjones4004/Panimalar-Innovation-Hub?style=for-the-badge&logo=github&color=f59e0b)](https://github.com/jeswinjones4004/Panimalar-Innovation-Hub/stargazers)
[![GitHub Forks](https://img.shields.io/github/forks/jeswinjones4004/Panimalar-Innovation-Hub?style=for-the-badge&logo=github&color=8b5cf6)](https://github.com/jeswinjones4004/Panimalar-Innovation-Hub/network)
[![License](https://img.shields.io/github/license/jeswinjones4004/Panimalar-Innovation-Hub?style=for-the-badge&color=22c55e)](LICENSE)
[![Issues](https://img.shields.io/github/issues/jeswinjones4004/Panimalar-Innovation-Hub?style=for-the-badge&color=ef4444)](https://github.com/jeswinjones4004/Panimalar-Innovation-Hub/issues)

![React](https://img.shields.io/badge/React_19-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)
![Vite](https://img.shields.io/badge/Vite-646CFF?style=for-the-badge&logo=vite&logoColor=white)
![TailwindCSS](https://img.shields.io/badge/Tailwind_CSS_v4-06B6D4?style=for-the-badge&logo=tailwind-css&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=node.js&logoColor=white)
![Express](https://img.shields.io/badge/Express_v5-000000?style=for-the-badge&logo=express&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-316192?style=for-the-badge&logo=postgresql&logoColor=white)
![Supabase](https://img.shields.io/badge/Supabase-3ECF8E?style=for-the-badge&logo=supabase&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=for-the-badge&logo=redis&logoColor=white)
![Sequelize](https://img.shields.io/badge/Sequelize-52B0E7?style=for-the-badge&logo=sequelize&logoColor=white)
![JWT](https://img.shields.io/badge/JWT-000000?style=for-the-badge&logo=JSON%20web%20tokens&logoColor=white)
![Vercel](https://img.shields.io/badge/Vercel-000000?style=for-the-badge&logo=vercel&logoColor=white)

[🚀 Live Demo](#) · [🐛 Report Bug](https://github.com/jeswinjones4004/Panimalar-Innovation-Hub/issues) · [✨ Request Feature](https://github.com/jeswinjones4004/Panimalar-Innovation-Hub/issues)

</div>

---

## 📋 Table of Contents

- [Overview](#-overview)
- [Features](#-features)
- [Architecture](#-architecture)
- [Tech Stack](#-tech-stack)
- [Database Schema](#-database-schema)
- [API Reference](#-api-reference)
- [Getting Started](#-getting-started)
- [Configuration](#-configuration)
- [Project Structure](#-project-structure)
- [Roles & Permissions](#-roles--permissions)
- [Contributing](#-contributing)
- [License](#-license)

---

## 🌟 Overview

> **A full-stack showcase platform built exclusively for Panimalar Engineering College's AIML Department — where students publish, discover, and celebrate real Machine Learning, Deep Learning, NLP, and Computer Vision projects.**

Academic projects built by students too often disappear into zip files and email threads, never seen by peers, faculty, or recruiters. **Panimalar Innovation Hub** solves this by providing a polished, searchable, role-gated platform where students can publish their AIML work with screenshots, demo videos, GitHub links, and live demos — all in one place.

Built with a production-grade stack (React 19 + Express 5 + PostgreSQL + Supabase + Redis), the platform supports three-tier role management (Student → Admin → Super Admin), Google OAuth, project approval workflows, a like/comment/save system, email notifications, and an admin activity audit trail.

### Why Panimalar Innovation Hub?

| Problem | Solution |
|---------|----------|
| Student projects have no visible home after submission | Persistent project cards with full media, live demo & GitHub links |
| No way to browse or discover peer work by category | Category filters (ML, DL, NLP, CV) + full-text search + trending sort |
| Unmoderated content in academic settings | Admin approval workflow before projects go public |
| Managing admins manually is error-prone | Super Admin dashboard to promote, demote, and audit all admins |
| Static portfolios don't show engagement | Like, comment, save, and view-count tracking per project |

---

## ✨ Features

<div align="center">

| Feature | Description |
|---------|-------------|
| 🔍 **Smart Project Explorer** | Search by title/description, filter by category (ML/DL/NLP/CV), sort by Trending, Most Liked, or Newest |
| 🔐 **JWT Authentication** | Secure registration & login with bcrypt-hashed passwords; Google OAuth via Supabase |
| 👤 **Student Profiles** | Rich profiles with bio, skills, roll number, year, section, GitHub & LinkedIn links |
| 📁 **Project Uploads** | Upload up to 5 screenshots and a demo video (10MB/file) stored in Supabase Storage |
| ✅ **Approval Workflow** | Submitted projects stay hidden until approved by an Admin or Super Admin |
| 👑 **3-Tier Role System** | Student → Admin (faculty-approved) → Super Admin (isolated dashboard) |
| 🔔 **Email Alerts** | Nodemailer sends Super Admin email notifications on new project submissions |
| ❤️ **Engagement System** | Like, comment, and save projects; real-time view & like counts on each project card |
| 📊 **Admin Panel** | Admins review pending projects, approve/reject, and manage their own submissions |
| 🛡️ **Super Admin Dashboard** | Completely isolated route — manage all admins, view audit logs, handle access requests |
| 📈 **Activity Audit Logs** | Every admin action (approve, reject, promote, demote) is logged with timestamp |
| ⚡ **Redis Caching** | Frequently accessed project lists cached in Redis to reduce database load |
| 📄 **PDF Export** | Students can export project details as PDF using jsPDF + html2canvas |
| 🎨 **Glassmorphism UI** | Dark-mode-first design with Framer Motion animations and fully responsive layout |
| ⚡ **Vercel Speed Insights** | Built-in performance monitoring via `@vercel/speed-insights` |

</div>

---

## 🏗️ Architecture

```mermaid
graph TD
    U[👤 Student / Visitor] --> FE[Frontend\nReact 19 + Vite + Tailwind v4]
    A[👨‍💼 Admin] --> FE
    SA[👑 Super Admin\n/super-admin route] --> FE

    FE -->|REST API calls via Axios| API[Express v5 API Server\nNode.js]

    API --> AUTH[Auth Routes\n/api/auth]
    API --> PROJ[Project Routes\n/api/projects]
    API --> USR[User Routes\n/api/users]
    API --> ADM[Admin Routes\n/api/admin]

    AUTH -->|JWT + bcrypt| DB[(PostgreSQL\nvia Sequelize ORM)]
    PROJ --> DB
    USR --> DB
    ADM --> DB

    PROJ -->|File Uploads| SUP[Supabase Storage\nScreenshots + Videos]
    AUTH -->|Google OAuth| SUP
    API -->|Cache hot queries| RDS[(Redis Cache)]
    API -->|New project alert| MAIL[Nodemailer\nEmail Alerts]

    DB --> MODELS[Models:\nUser · Project · Comment\nActivityLog · AdminRequest\nProjectLikes · SavedProjects · ProjectViews]
```

The frontend is a React 19 SPA served by Vite. All API traffic flows through the Express v5 backend, which uses Sequelize to manage a PostgreSQL database (locally or via `DATABASE_URL` for hosted providers like Render/Supabase). Media files go directly to Supabase Storage. Redis sits in front of the project list endpoint to reduce database round-trips on hot queries. Nodemailer fires email alerts to the Super Admin on each new project submission.

---

## 🛠️ Tech Stack

### Frontend
| Technology | Purpose | Version |
|------------|---------|---------|
| React | UI framework | ^19.2.4 |
| Vite | Build tool & dev server | ^8.0.1 |
| Tailwind CSS | Utility-first styling | ^4.2.2 |
| Framer Motion | Animations & transitions | ^12.38.0 |
| React Router DOM | Client-side routing | ^7.13.1 |
| Axios | HTTP client | ^1.13.6 |
| Lucide React | Icon library | ^0.577.0 |
| @react-oauth/google | Google OAuth integration | ^0.13.4 |
| @supabase/supabase-js | Supabase client (auth + storage) | ^2.103.0 |
| react-hot-toast | Toast notifications | ^2.6.0 |
| jsPDF + html2canvas | PDF export | ^4.2.1 / ^1.4.1 |
| @vercel/speed-insights | Performance monitoring | ^2.0.0 |

### Backend
| Technology | Purpose | Version |
|------------|---------|---------|
| Node.js | Runtime | v16+ |
| Express | Web framework | ^5.2.1 |
| Sequelize | ORM | ^6.37.5 |
| PostgreSQL (pg) | Primary database | ^8.11.3 |
| Redis | Caching layer | ^5.12.1 |
| JWT (jsonwebtoken) | Stateless auth tokens | ^9.0.3 |
| bcryptjs | Password hashing | ^3.0.3 |
| Multer | File upload middleware | ^2.1.1 |
| @supabase/supabase-js | Storage uploads | ^2.103.0 |
| Nodemailer | Email notifications | ^8.0.4 |
| google-auth-library | Google token verification | ^10.6.2 |
| dotenv | Environment config | ^17.3.1 |
| nodemon | Dev auto-restart | ^3.1.14 |

### Infrastructure
| Technology | Purpose |
|------------|---------|
| PostgreSQL | Relational database (local or hosted) |
| Supabase | File storage + Google OAuth provider |
| Redis | In-memory caching |
| Vercel | Frontend deployment |
| Render / Supabase | Backend + DB deployment options |

---

## 🗄️ Database Schema

```mermaid
erDiagram
    User {
        UUID id PK
        STRING name
        STRING email
        STRING password
        STRING role
        STRING avatar
        TEXT bio
        ARRAY skills
        STRING rollNo
        STRING year
        STRING section
        STRING department
        STRING github
        STRING linkedin
        STRING authProvider
    }

    Project {
        UUID id PK
        STRING title
        TEXT description
        STRING category
        STRING githubLink
        STRING demoLink
        STRING liveLink
        ARRAY techStack
        ARRAY screenshots
        UUID creatorId FK
        BOOLEAN isApproved
        INTEGER views
        INTEGER likesCount
    }

    Comment {
        UUID id PK
        UUID projectId FK
        UUID userId FK
        TEXT content
    }

    ActivityLog {
        UUID id PK
        UUID adminId FK
        STRING action
        STRING targetType
        UUID targetId
    }

    AdminRequest {
        UUID id PK
        UUID userId FK
        STRING status
        TEXT reason
    }

    User ||--o{ Project : "creates"
    User ||--o{ Comment : "writes"
    User ||--o{ ActivityLog : "generates"
    User ||--o{ AdminRequest : "submits"
    Project ||--o{ Comment : "has"
    User }o--o{ Project : "likes (ProjectLikes)"
    User }o--o{ Project : "saves (SavedProjects)"
    User }o--o{ Project : "views (ProjectViews)"
```

---

## 📡 API Reference

### Base URL
```
http://localhost:5000/api
```

### Authentication
All protected routes require a Bearer token in the `Authorization` header:
```
Authorization: Bearer <jwt_token>
```

### Auth Endpoints

| Method | Endpoint | Auth | Description |
|--------|----------|------|-------------|
| `POST` | `/auth/register` | Public | Register a new student account |
| `POST` | `/auth/login` | Public | Login and receive JWT token |
| `POST` | `/auth/supabase` | Public | Login or register via Supabase (Google OAuth) |

### Project Endpoints

| Method | Endpoint | Auth | Description |
|--------|----------|------|-------------|
| `GET` | `/projects` | Public | List approved projects (search, filter, sort, paginate) |
| `GET` | `/projects/recommended` | Public | Get AI-recommended projects |
| `GET` | `/projects/:id` | Public | Get single project details |
| `POST` | `/projects` | 🔐 Student | Create project (multipart: screenshots + demoVideo) |
| `PUT` | `/projects/:id` | 🔐 Owner | Update project (multipart) |
| `DELETE` | `/projects/:id` | 🔐 Owner | Delete project |
| `POST` | `/projects/:id/like` | 🔐 Student | Toggle like on a project |
| `POST` | `/projects/:id/comment` | 🔐 Student | Add comment to project |
| `PUT` | `/projects/:id/approve` | 🔐 Admin+ | Approve or reject project |

**Query Parameters for `GET /projects`:**

| Param | Example | Description |
|-------|---------|-------------|
| `category` | `ML` | Filter by ML, DL, NLP, CV |
| `search` | `image%20classification` | Full-text search on title & description |
| `sort` | `trending` | Options: `trending`, `most_liked`, `newest` |
| `year` | `2024` | Filter by submission year |
| `tech` | `PyTorch` | Filter by tech stack item |
| `page` | `2` | Pagination page number |
| `limit` | `12` | Results per page (default: 12) |

### Admin Endpoints

| Method | Endpoint | Auth | Description |
|--------|----------|------|-------------|
| `POST` | `/admin/request-access` | 🔐 Student | Submit request for Admin role |
| `GET` | `/admin/requests` | 👑 Super Admin | List all pending Admin requests |
| `PUT` | `/admin/requests/:id` | 👑 Super Admin | Approve or reject Admin request |
| `GET` | `/admin/list` | 👑 Super Admin | List all current Admins |
| `PUT` | `/admin/demote/:id` | 👑 Super Admin | Demote Admin back to Student |
| `GET` | `/admin/logs` | 👑 Super Admin | View full activity audit log |

---

## 🚀 Getting Started

### Prerequisites

- **Node.js** >= v16
- **PostgreSQL** >= 13 (local) or a `DATABASE_URL` (Supabase / Render / Neon)
- **Redis** running on `localhost:6379` (or a Redis Cloud URL)
- A **Supabase** project for file storage and Google OAuth
- Optional: **nodemon** for development auto-restart

### Installation

**1. Clone the repository**
```bash
git clone https://github.com/jeswinjones4004/Panimalar-Innovation-Hub.git
cd Panimalar-Innovation-Hub
```

**2. Backend Setup**
```bash
cd backend
npm install
```

Create a `.env` file in the `backend/` directory (see [Configuration](#-configuration) below).

**3. Start the Backend Server**
```bash
# Development (auto-restart)
npm run dev

# Production
npm start
```

The API will be available at `http://localhost:5000`.

**4. Frontend Setup**
```bash
cd ../frontend
npm install
npm run dev
```

Open `http://localhost:5173` in your browser.

**5. (Optional) Seed Sample Data**
```bash
cd backend
node seed.js
```
This creates 3 dummy student accounts (password: `password123`) and 4 sample AIML projects.

---

## ⚙️ Configuration

Create a `.env` file inside the `backend/` directory:

| Variable | Required | Description |
|----------|----------|-------------|
| `PORT` | ⚠️ | Server port (default: `5000`) |
| `DATABASE_URL` | ✅ | Full PostgreSQL connection URL (e.g. Supabase / Neon / Render). Overrides individual DB vars. |
| `DB_HOST` | ⚠️ | DB host if not using `DATABASE_URL` (default: `localhost`) |
| `DB_PORT` | ⚠️ | DB port (default: `5432`) |
| `DB_NAME` | ⚠️ | Database name |
| `DB_USER` | ⚠️ | Database user |
| `DB_PASS` | ⚠️ | Database password |
| `DB_SSL` | ⚠️ | Set `true` to enable SSL for hosted DB |
| `JWT_SECRET` | ✅ | Secret key for signing JWT tokens |
| `SUPABASE_URL` | ✅ | Supabase project URL (for file storage) |
| `SUPABASE_SERVICE_KEY` | ✅ | Supabase service role key |
| `FRONTEND_URL` | ⚠️ | Frontend origin for CORS (default: `http://localhost:5173`) |
| `RENDER_EXTERNAL_URL` | ⚠️ | Set automatically by Render — used to format media URLs |
| `GMAIL_USER` | ⚠️ | Gmail address for Nodemailer alerts |
| `GMAIL_PASS` | ⚠️ | Gmail app password for Nodemailer |
| `REDIS_URL` | ⚠️ | Redis connection URL (default: `redis://localhost:6379`) |

**Example `.env`:**
```env
PORT=5000
DATABASE_URL=postgresql://user:pass@db.supabase.co:5432/postgres
JWT_SECRET=your_super_secret_jwt_key
SUPABASE_URL=https://xxxx.supabase.co
SUPABASE_SERVICE_KEY=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...
FRONTEND_URL=http://localhost:5173
GMAIL_USER=you@gmail.com
GMAIL_PASS=your_app_password
```

---

## 📁 Project Structure

```
Panimalar-Innovation-Hub/
├── backend/
│   ├── config/
│   │   └── db.js                 # Sequelize + PostgreSQL connection
│   ├── controllers/
│   │   ├── authController.js     # Register, login, Supabase OAuth
│   │   ├── projectController.js  # CRUD, like, comment, approve, recommend
│   │   ├── adminController.js    # Admin requests, audit logs, demotion
│   │   └── userController.js     # Profile management
│   ├── middleware/
│   │   ├── authMiddleware.js     # JWT protect, role guards
│   │   └── uploadMiddleware.js   # Multer (10MB limit)
│   ├── models/
│   │   ├── User.js
│   │   ├── Project.js
│   │   ├── Comment.js
│   │   ├── ActivityLog.js
│   │   ├── AdminRequest.js
│   │   └── index.js              # Associations & Sequelize sync
│   ├── routes/
│   │   ├── auth.js
│   │   ├── projects.js
│   │   ├── users.js
│   │   └── admin.js
│   ├── utils/
│   │   ├── mailer.js             # Nodemailer Super Admin alerts
│   │   ├── supabaseStorage.js    # File upload to Supabase Storage
│   │   └── eventEmitter.js       # Internal event bus
│   ├── seed.js                   # Dev data seeder
│   ├── server.js                 # Express app entry point
│   └── package.json
│
└── frontend/
    ├── src/
    │   ├── components/
    │   │   ├── Navbar.jsx
    │   │   ├── Footer.jsx
    │   │   └── ScrollToTop.jsx
    │   ├── context/
    │   │   └── AuthContext.jsx   # Global auth state
    │   ├── pages/
    │   │   ├── Home.jsx
    │   │   ├── Projects.jsx
    │   │   ├── ProjectDetails.jsx
    │   │   ├── Dashboard.jsx     # Student project management
    │   │   ├── Profile.jsx
    │   │   ├── AdminPanel.jsx
    │   │   ├── SuperAdminDashboard.jsx  # Isolated super admin UI
    │   │   ├── Login.jsx
    │   │   ├── AdminLogin.jsx
    │   │   ├── Register.jsx
    │   │   └── GithubCallback.jsx
    │   └── App.jsx               # Router + layout
    ├── index.html
    └── package.json
```

---

## 🔐 Roles & Permissions

| Action | Visitor | Student | Admin | Super Admin |
|--------|---------|---------|-------|-------------|
| Browse & search projects | ✅ | ✅ | ✅ | ✅ |
| View project details | ✅ | ✅ | ✅ | ✅ |
| Register / Login | ✅ | ✅ | ✅ | ✅ |
| Submit project | ❌ | ✅ | ✅ | ✅ |
| Edit / Delete own project | ❌ | ✅ | ✅ | ✅ |
| Like & comment | ❌ | ✅ | ✅ | ✅ |
| Save projects | ❌ | ✅ | ✅ | ✅ |
| Request Admin role | ❌ | ✅ | ❌ | ❌ |
| Approve / Reject projects | ❌ | ❌ | ✅ | ✅ |
| View activity logs | ❌ | ❌ | ❌ | ✅ |
| Promote / Demote admins | ❌ | ❌ | ❌ | ✅ |
| Handle admin access requests | ❌ | ❌ | ❌ | ✅ |

The Super Admin dashboard runs on the `/super-admin` route with a completely isolated layout (no shared Navbar/Footer) to prevent accidental exposure.

---

## 🤝 Contributing

Contributions from AIML department students and faculty are welcome!

1. Fork the repository
2. Create your feature branch
   ```bash
   git checkout -b feature/your-feature-name
   ```
3. Commit your changes
   ```bash
   git commit -m "feat: add your feature description"
   ```
4. Push to your branch
   ```bash
   git push origin feature/your-feature-name
   ```
5. Open a Pull Request against `main`

Please make sure your changes don't break existing API contracts and that new backend routes are protected by the appropriate middleware (`protect`, `adminOrSuperAdmin`, `superAdmin`).

---

## 📄 License

Distributed under the ISC License. See [`LICENSE`](LICENSE) for details.

---

<div align="center">

Built with ❤️ by [Jeswin Jones](https://github.com/jeswinjones4004) for **Panimalar Engineering College — AIML Department**

⭐ Star this repo if it helped you!

<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=12,20,24&height=120&section=footer" width="100%"/>

</div>
