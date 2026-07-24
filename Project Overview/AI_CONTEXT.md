# AI Context & Assistant Guidelines

## Project Architecture
WorkSphere Enterprise is a dual-backend (Node.js/Prisma & Spring Boot/Java) system with a massive React SPA frontend.

## Folder Structure Rules
- Frontend code lives in `frontend/src`.
- Role-specific pages MUST go into `frontend/src/modules/<role_name>/`.
- Shared components go into `frontend/src/components/`.
- Backend Node code is in `backend/src/`.
- Backend Java code is in `backend/src/main/java/`.

## Coding Style
- **Frontend:** Functional React components, TailwindCSS for styling, Lucide-React for icons. Strict TypeScript.
- **Backend (Node):** Express.js, Prisma ORM.

## Current Implementation State
- UI shells and dashboards for all roles are created.
- Production ESLint errors have been resolved.
- Database schemas are designed but may need expansion as features grow.

## Development Directives for AI
- Always verify ESLint rules before modifying React components (e.g., avoid creating components inside render functions).
- Do not invent generic filler code. Read the existing models in `backend/src/models` or `database/prisma` when writing backend logic.
- Keep Tailwind classes clean and utilize the established color palette (slate, indigo, emerald, rose).
