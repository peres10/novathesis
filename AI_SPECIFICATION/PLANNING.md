# Project Planning & Roadmap

## 1. Methodology
- **Agile/Scrum:** Iterative development with frequent feedback loops.
- **Vibe Coding:** Accelerated prototyping using AI-assisted tools (Bolt.new, Lovable) to generate UI and core CRUD logic.
- **Progressive Refinement:** Moving from an AI-generated prototype to a hardened, maintainable Spring Boot + React codebase.

## 2. Development Phases

### Phase 1: March - Environment Setup & Initial Prototyping
- Build initial React/Supabase prototype with Vibe Coding tools.
- Focus: Company registration, proposal submission, basic student interaction.
- Set up development environment and basic CI/CD routines.

### Phase 2: April - Coverage Expansion
- Extend prototype: Student ranking, basic seriation logic, simple notifications.
- Align PostgreSQL schema with formal ERD.
- **Transition Start:** Introduce Spring Boot backend for selected core use cases (e.g., proposal validation).

### Phase 3: May - Backend Consolidation
- Expand Spring Boot backend to cover main business logic.
- Reduce reliance on Supabase-only functionalities.
- Implement REST API endpoints and OAuth authentication with university IdP.
- Introduce structured audit logging.

### Phase 4: June - Core Workflows & Hardening
- Complete end-to-end workflows: Submission -> Validation -> Clarification -> Candidacies -> Seriation.
- Refine database schema based on performance observations.
- Expand automated testing (Unit/Integration tests).

### Phase 5: July - Advanced Features & Optimization
- Implement company proposal limits per edition.
- Add export capabilities (CSV/JSON).
- Improve admin tools (Superuser support, configuration screens).
- Optimize performance for dashboards and API calls.

### Phase 6: August - Validation & Final Documentation
- System validation against all functional/non-functional requirements.
- Collect stakeholder feedback and prioritize final adjustments.
- Finalize technical documentation (APIs, deployment notes).

### Phase 7: September - Thesis Writing & Polish
- Focus on finalizing the dissertation document.
- Perform minor fixes or polish to the platform.

## 3. Critical Milestones
1. **End of March:** Functional prototype of core submission flow.
2. **End of May:** Functional Spring Boot backend with OAuth.
3. **End of June:** Fully automated seriation and assignment workflow.
4. **End of August:** Production-ready platform prototype.
