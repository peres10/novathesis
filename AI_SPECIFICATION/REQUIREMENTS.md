# System Requirements

## 1. Functional Requirements (FR)

### Edition & Configuration Management
- **FR-11:** Create new academic editions (Undergraduate Internship vs. Master’s).
- **FR-12:** Define and manage time slots for company presentations.
- **FR-13:** Create/edit reusable email templates with dynamic variables.
- **FR-14:** Maintain edition-specific info pages (FAQs, Regulations).
- **FR-15:** Publish targeted news/announcements.

### Proposal Submission & Classification
- **FR-21:** Detailed submission for companies/professors (objectives, requirements, benefits).
- **FR-22:** Feedback loop for coordinators to request clarifications.
- **FR-23:** Accept, conditionally accept, or reject proposals.
- **FR-24:** Duplicate proposals from previous editions.
- **FR-25:** Book presentation time slots.
- **FR-26:** Deadline notifications (email/in-app).

### Student Applications & Seriation
- **FR-31:** Browse proposals and rank preferences in order.
- **FR-32:** Submit supporting docs (CV, motivation letter).
- **FR-33:** **Automated Seriation Algorithm:** Rank students based on ECTS completed and grade average.
- **FR-35:** Companies view ranked lists and manage selections.
- **FR-36:** Exclude/deselect candidates from ranked lists.

### User & Company Management
- **FR-41:** Validate new company registrations and protocols.
- **FR-42:** Manage company hierarchy (parent companies/departments).
- **FR-43:** Manage company employee accounts and mentors.
- **FR-44:** **Superuser Access:** Coordinators can access other accounts for support (fully audited).
- **FR-45:** Bulk import users (Students, Professors) via CSV.

### Reporting & Data Export
- **FR-61:** Export lists (Students, Proposals, Assignments) in CSV/JSON.
- **FR-62:** Maintain detailed audit logs for all critical system actions.

## 2. Non-Functional Requirements (NFR)

- **NFR-SEC-1:** Database Row-Level Security (RLS) for data isolation.
- **NFR-AUD-1:** Immutable, tamper-evident audit logs.
- **NFR-REL-1:** High email deliverability for time-sensitive notifications.
- **NFR-PERF-1:** Page loads < 3 seconds; API latency < 500ms.
- **NFR-PERF-2:** Real-time dashboard updates (WebSockets).
- **NFR-USAB-1:** Responsive, mobile-friendly UI.
- **NFR-MAINT-1:** Modular, layered architecture for independent evolution.
