# Multi-Tenant Feature Flag Management System

## How to Run

### Backend
cd backend
npm install
node server.js

### Frontend
Open these files directly in Chrome:
- super-admin/index.html
- admin/index.html
- user/index.html

## Super Admin Credentials
Email: admin@system.com
Password: superadmin123

## Tech Decisions

### Why SQLite?
Zero setup, no separate server needed, perfect for this scope.

### Why JWT?
Stateless, easy to implement custom auth without third-party providers.

### Why plain HTML/JS?
No build tools needed, faster to develop, simple to run.

### Why bcryptjs?
Secure password hashing, industry standard.

## API Endpoints

### Auth
POST /api/auth/super-admin/login
POST /api/auth/admin/signup
POST /api/auth/admin/login

### Organizations
POST   /api/organizations        (super admin only)
GET    /api/organizations        (super admin only)
GET    /api/organizations/public (public)

### Feature Flags
GET    /api/flags                (org admin only)
POST   /api/flags                (org admin only)
PATCH  /api/flags/:id            (org admin only)
DELETE /api/flags/:id            (org admin only)
GET    /api/flags/check          (public)

## Folder Structure
feature-flag-system/
├── backend/
│   ├── routes/
│   ├── middleware/
│   ├── db.js
│   └── server.js
├── super-admin/index.html
├── admin/index.html
└── user/index.html
