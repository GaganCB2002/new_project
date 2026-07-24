# Complete File Structure

## High-Level Directory Tree
```
WorkSphere Enterprise/
├── frontend/             # React SPA (Vite)
│   ├── src/
│   │   ├── modules/      # Role-specific modules (CEO, HR, Employee, etc.)
│   │   ├── components/   # Shared UI components
│   │   ├── hooks/        # Custom React hooks
│   │   ├── store/        # Redux/Zustand state
│   │   └── utils/        # Helper functions
├── backend/              # Dual Backend Environment
│   ├── src/              # Node.js Express API
│   │   ├── routes/
│   │   ├── controllers/
│   │   ├── services/
│   │   ├── models/       # Mongoose/Prisma models
│   │   └── main/java/    # Spring Boot Enterprise API
├── database/             # Schemas, Migrations, Seeders
│   ├── prisma/
│   └── schema/           # Raw SQL exports
├── docs/                 # Internal Architecture Docs
└── Project Overview/     # High-level Documentation
```

## Purpose of Each Folder
- **frontend/src/modules:** Contains isolated business logic and pages for each of the 15+ roles. Ensures code splitting and minimal bundle size.
- **backend/src/main/java:** The Java enterprise backend for heavy computing and strict typed transactional integrity.
- **backend/src/services:** The Node.js services handling real-time WebSockets and fast I/O.
- **database:** Contains the source of truth for the database schema, including triggers and stored procedures.
