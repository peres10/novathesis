# Data Model Specification

## 1. Core Entities

### User & Identity
- **User:** `id`, `name`, `email`, `accountCreationDate`, `status`
- **UserRole:** `id`, `roleName`
- **UserRoleAssignment:** `userID`, `roleID`
- **Student:** `studentNumber` (PK), `userID`, `imageID`, `cvFileID`
- **Professor:** `professorID` (PK), `userID`, `scientificField`, `category`, `phoneNumber`, `office`, `url`
- **CompanyEmployee:** `id`, `companyID`, `userID`, `department`, `contact`, `biography`

### Organizations
- **Company:** `id`, `parentCompanyID`, `responsibleEmployeeID`, `addressID`, `name`, `acronym`, `nipc`, `website`, `phoneNumber`, `status`, `creationDate`
- **Address:** `id`, `address`, `locality`, `postalCode`, `country`

### Academic Structure
- **Edition:** `id`, `name`, `description`, `year`, `semester`, `type` (Undergrad vs Master), `status`
- **EditionDates:** `editionID`, `dateStart`, `dateEndProposals`, `dateStartChoices`, `dateEndChoices`, `dateStartExecution`, `dateEndExecution`, etc.
- **EditionCoordinator:** `editionID`, `coordinatorID`, `isMainCoordinator`

### Proposals & Applications
- **Proposal:** `id`, `submitterID` (Company/Professor), `professorSubmitterID`, `title`, `description`, `objectives`, `workPlan`, `expectedResults`, `formation`, `preRequirements`, `keywords`, `scientificField`, `status`, `type`, `benefits`, `selectionProcess`, `local`
- **EditionProposal:** `editionID`, `proposalID`
- **Application:** `id`, `proposalID`, `studentNumber`, `editionID`, `preferenceRank`, `updatedAt`
- **Assignment:** `id`, `applicationID`, `status`, `createdAt`, `updatedAt`
- **ProposalFeedback:** `interactionID`, `proposalID`, `proposalUpdatedAfterFeedback`

### Supporting Data
- **StudentAcademicData:** `studentID`, `currentECTS`, `averageGrade`, `gradeCS`, `updateDate`
- **Interaction:** `id`, `authorID`, `destinationID`, `date`, `type`, `message`, `attachment`, `requiresAction`
- **File / Image:** Metadata for uploads (`filename`, `filesize`, `filetype`, etc.)

## 2. Key Relationships
- **User -> Roles:** Many-to-Many via `UserRoleAssignment`.
- **Student/Professor/Employee -> User:** One-to-One (Inheritance/Profile extension).
- **Proposal -> Edition:** Many-to-Many via `EditionProposal`.
- **Application -> Student/Proposal/Edition:** Junction entity for rankings.
- **Assignment -> Application:** Outcome of the seriation process.
- **Company -> Address:** Many-to-One.
- **Company -> Company:** Recursive relationship for organizational hierarchy.
