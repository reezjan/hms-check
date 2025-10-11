# Hotel Management System

## Overview
This project is a comprehensive hotel management system designed to streamline hotel operations. It provides a multi-role, integrated platform for managing guest services, room/hall, restaurant/bar operations, inventory, staff, tasks, maintenance, finance, and vendor management. The system aims to enhance efficiency across all hotel departments.

## User Preferences
I prefer detailed explanations and an iterative development approach. Please ask before making major changes. Do not make changes to the `shared/` folder unless absolutely necessary and with prior approval. Do not modify the core authentication logic in `server/auth.ts` without explicit instruction.

## System Architecture
The system is a full-stack application built with React and TypeScript for the frontend, and Express.js with Node.js for the backend. PostgreSQL is used as the primary database, managed with Drizzle ORM.

**Frontend:**
-   **Framework**: React 18 with Vite.
-   **Styling**: TailwindCSS, shadcn/ui, and Radix UI.
-   **Routing**: Wouter.
-   **State Management**: TanStack Query.

**Backend:**
-   **Framework**: Express.js.
-   **Authentication**: Passport.js with multi-role support (17 distinct roles).
-   **Database ORM**: Drizzle ORM for type-safe PostgreSQL interactions.

**Key Features:**
-   **Comprehensive Management Modules**: Guest/customer, room/hall, restaurant/bar operations, inventory, staff, task assignment, maintenance, financial, and vendor management.
-   **UI/UX**: Role-specific dashboards focusing on functionality and clarity.
-   **API Design**: All API routes are prefixed with `/api`.
-   **Database Management**: Drizzle Kit for schema migrations; manual SQL changes are prohibited.
-   **Unified Development Server**: Single server on port 5000 for both frontend and backend.
-   **Hierarchical Leave Approval System**: Multi-level workflow with subordinate filtering and role-based access.
-   **Room Reservation & Check-in/Check-out System**: Includes double-booking prevention and automatic cleaning queue integration.
-   **Restaurant Billing System**: Features multi-table selection, cascading tax, split bills, multiple payment methods, and audit trails.
-   **Immutable Financial System**: Transactions are permanent with void-only functionality requiring justification and approval.
-   **Enterprise-Grade Security**: Production-ready API authentication/authorization with hotel ownership verification.
-   **Dual Reporting System**: Separate dashboards for financial analytics and complete operational transparency.
-   **Security Hardening**: Includes fixes for null byte injection, authorization bypass, input validation (SQL injection, XSS, type coercion), secure financial transactions, maintenance request reassignment security, and room status manipulation prevention with audit logging.
-   **Password Security**: Passwords can only be changed via a dedicated reset endpoint, preventing direct modification via user update routes.

## External Dependencies
-   **PostgreSQL**: Relational database.
-   **Vite**: Frontend build tool.
-   **Wouter**: Frontend routing library.
-   **TailwindCSS**: CSS framework.
-   **shadcn/ui & Radix UI**: UI component libraries.
-   **TanStack Query**: Data fetching and state management.
-   **Express.js**: Backend web framework.
-   **Node.js**: JavaScript runtime.
-   **Drizzle ORM**: TypeScript ORM for PostgreSQL.
-   **Passport.js**: Authentication middleware.
-   **Lucide icons**: Icon library.

## Replit Environment Setup (October 11, 2025)

### Initial Setup Completed
The project has been successfully configured to run in the Replit environment:

1. **Database**: PostgreSQL database provisioned and seeded with test data
   - 17 distinct user roles (super_admin, owner, manager, etc.)
   - Test hotel with rooms, halls, restaurant tables, and menu items
   - Sample users, guests, vendors, and financial transactions
   - Default login: username `superadmin`, password `aef009750905865270b03eb27ceba80e`

2. **Development Workflow**: Configured to run `npm run dev` on port 5000
   - Frontend and backend served from single Express server
   - Vite dev server properly configured with `allowedHosts: true` for Replit proxy
   - WebSocket support for real-time updates

3. **Deployment**: Configured for autoscale deployment
   - Build: `npm run build` (compiles Vite frontend + esbuild backend)
   - Run: `npm start` (production server)

4. **Scripts Available**:
   - `npm run dev` - Development server with hot reload
   - `npm run build` - Production build
   - `npm start` - Start production server
   - `npm run db:push` - Push database schema changes
   - `npm run db:seed` - Seed database with test data

### Test Credentials
- **Superadmin**: username `superadmin`, password `aef009750905865270b03eb27ceba80e`
- **Owner**: username `owner`, password `owner123`
- **Manager**: username `manager`, password `manager`
- **Waiter**: username `waiter`, password `waiter`
- See seed script output for more test users