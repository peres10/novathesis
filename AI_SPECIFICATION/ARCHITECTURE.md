# Technical Architecture & Stack

## 1. Overview
A unified web platform for managing internship and dissertation proposals at NOVA FCT, following a three-layer architecture (Presentation, Application, and Data).

## 2. Tech Stack
- **Frontend:** React with Next.js (TypeScript).
- **Styling:** Tailwind CSS (preferred for rapid prototyping) or Vanilla CSS.
- **Backend (Phase 1):** Supabase (BaaS) for Auth, Database, and Edge Functions.
- **Backend (Phase 2):** Spring Boot (Java) for complex business logic (seriation, auditing).
- **Database:** PostgreSQL (Relational Model).
- **Authentication:** OAuth integration with University Identity Provider (IdP).
- **File Storage:** Supabase Storage (or S3-compatible) for CVs and legal protocols.
- **Email:** Transactional Email Service (e.g., Resend, SendGrid) with authenticated outbound protocols.

## 3. High-Level Layers
1. **Presentation Layer:**
   - Role-specific dashboards (Student, Professor, Company, Coordinator, Secretariat).
   - Reusable component library for consistency.
2. **Application Layer:**
   - REST API endpoints.
   - Business logic for student seriation and assignment.
   - Real-time updates via WebSockets/SSE for critical dashboards.
3. **Data Layer:**
   - PostgreSQL with Row-Level Security (RLS) for data isolation.
   - Referential integrity enforced via Foreign Keys.
   - JSONB support for semi-structured data (e.g., email templates, feedback).

## 4. Security & Compliance
- **RBAC:** Role-Based Access Control with granular permissions.
- **Audit Logging:** Immutable, tamper-evident logs for all critical actions.
- **Data Encryption:** TLS for data in transit; secure hashing (Argon2/bcrypt) for credentials.
