# Core Use Cases & Workflows

## 1. Student Flows

### UC-01: Student Ranks Preferences
1. **Log In:** Student enters via University OAuth.
2. **Browse:** Views all approved proposals for their edition.
3. **Filter:** Sorts by scientific field or company.
4. **Rank:** Selects and orders top-N preferences.
5. **Submit:** System validates the number of choices and saves the ranking with a timestamp.

### UC-07: Submit Support Documentation
- Triggered if a coordinator or proposal requires a CV or motivation letter.
- Student uploads PDF files to the platform.
- System links files to the student profile and specific application.

## 2. Coordinator Flows

### UC-05: Create New Edition
1. **Setup:** Coordinator defines edition name, year, and type.
2. **Timeline:** Sets deadlines for proposal submission, student ranking, and seriation.
3. **Constraints:** Sets max proposals per company/professor.
4. **Logic:** Configures seriation weights (ECTS vs. Average Grade).

### UC-02: Validate Proposal & Feedback Loop
1. **Review:** Coordinator views "Pending Validation" proposals.
2. **Feedback:** Annotates specific fields requiring clarification.
3. **Action:** Changes status to "Awaiting Clarification" or "Accepted".
4. **Notify:** System sends email to the submitter with feedback details.

### UC-03: Execute Student Seriation (The "Core Algorithm")
1. **Trigger:** Coordinator starts the seriation process after the ranking deadline.
2. **Process:**
   - Retrieves all student preferences.
   - Calculates a composite score: `(ECTS_Weight * Student_ECTS) + (Average_Grade_Weight * Student_Avg)`.
   - Sorts students by score.
   - **Matching:** Assigns students to proposals based on priority and availability.
3. **Results:** Generates assignment list and notifies all parties.

## 3. Submitter Flows (Company/Professor)

### UC-06: Register & Submit Initial Proposal
1. **Onboard:** Company rep fills registration form.
2. **Validation:** Secretariat verifies legal protocol signature.
3. **Submit:** User enters proposal details (objectives, local, benefits).
4. **Submit:** System saves as "Pending Validation" and notifies the coordinator.

### UC-08: View Assigned Candidates & Schedule Interviews
1. **Access:** Submitter views the ranked list of students assigned to their proposal.
2. **Contact:** Views student CVs and contact info.
3. **Interview:** Schedules interviews outside the platform (tracking status within).
4. **Confirm:** Formally confirms the final assignment.

## 4. Administrative Flows

### UC-11: Superuser Access
- Coordinator impersonates a student or professor account to resolve data inconsistencies or support issues.
- **Mandatory:** Every action performed during impersonation is logged with a justification in the audit trail.
