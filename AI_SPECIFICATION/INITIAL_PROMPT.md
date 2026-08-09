# Master AI Prompt: Phase 1 Implementation

## Project Overview
Build a "Dissertation and Internship Management Platform" for NOVA FCT. The platform unifies the lifecycle of undergraduate internships and Master's dissertations into a single digital ecosystem, replacing manual email/spreadsheet processes.

## Core Objective for this Version (Phase 1)
Implement the foundational infrastructure and the "Proposal Submission" workflow. This includes user onboarding, edition configuration by coordinators, and proposal submission by companies/professors.

## Key Roles & Access Control
1. **Edition Coordinator:** Can create/configure "Editions" (e.g., 2025/2026 Master's) and validate submitted proposals.
2. **Company Representative:** Can register their company and submit internship/project proposals.
3. **Professor:** Can submit scientific dissertation themes.
4. **Student:** Can browse approved proposals and submit a ranked list of preferences.

## Initial Feature Set
### 1. Edition & Admin Setup
- Dashboard for Coordinators to create a new "Edition" with:
  - Type (Undergraduate Internship or Master's Dissertation).
  - Key dates (Proposal submission window, Student ranking window).
  - Status (Draft, Active, Closed).

### 2. Company Onboarding & Validation
- Registration form for Company Representatives (Name, Email, Company Details, Legal identifiers).
- Validation queue for Coordinators to approve new company registrations.

### 3. The Proposal Workflow
- Submission form for Companies and Professors to create "Proposals" with:
  - Title, Objectives, Technical Requirements, Location, Benefits, and Supervisor details.
- Feedback Loop: Coordinators can view "Pending" proposals and either "Accept" or "Request Clarification" (adding comments).
- Submitter dashboard to see proposal status (Draft, Pending, Awaiting Clarification, Accepted).

### 4. Basic Student Interaction
- Browse Approved Proposals: A searchable list/grid of proposals marked as "Accepted" for the active edition.
- Preference Ranking: A simple interface where students can select their Top 5 proposals and drag-and-drop to rank them.

## Data Model Requirements
- **Users:** ID, Name, Email, Role.
- **Companies:** ID, Name, Status (Pending/Active), Address.
- **Editions:** ID, Year, Type, Start/End Dates.
- **Proposals:** ID, SubmitterID, EditionID, Title, Description, Status (Pending/Accepted/Clarification), Coordinator Feedback (JSON/Text).
- **Applications:** ID, StudentID, ProposalID, Rank (Integer).

## UI/UX Guidelines
- Clean, academic, and professional aesthetic (similar to a university portal).
- Role-based Sidebars: Different navigation items based on the user's role.
- Status Indicators: Clear visual cues (labels/colors) for proposal and registration statuses.
- Responsive Design: Must work on desktop and mobile.
