# Skill: Requirement-aligned Planning for React Medical Products

## Purpose
This skill captures the project planning and requirement mapping process for the React-Medical-Products app, ensuring work is directly aligned to the features listed in `Project_Requirements.md` (SRS document).

## Scope
- Analyze the current codebase (React frontend + Node/Express backend + MongoDB) relative to the SRS.
- Map each feature requirement from `Project_Requirements.md` to concrete implementation tasks.
- Produce planning artifacts (project plan, milestone list, task breakdowns) that reference requirement IDs.
- Provide guidance on how to build and validate each requirement (auth, product browsing, admin tools, chat integration, etc.).

## Tools & Technologies
This project primarily uses the following stack and tools:
- **Frontend:** React, React Router, CSS modules / CSS
- **Backend:** Node.js, Express.js
- **Database:** MongoDB with Mongoose ODM
- **Authentication:** JWT (JSON Web Tokens)
- **Email:** Nodemailer (or similar SMTP service)
- **Dev Tools:** ESLint, Prettier, nodemon, Postman (for API testing)

## Requirement Coverage (from `Project_Requirements.md`)
1. **User Authentication** (FR-AUTH-001..007)
2. **Product Management & Discovery** (FR-PROD-001..007)
3. **Admin Dashboard & Messaging** (FR-ADMIN-001..003b)
4. **Newsletter & Notifications** (FR-ADMIN-004..006)
5. **UI/UX & Performance** (Sections 3.3, 3.4, 3.5)
6. **Live Chat Integration** (added from requirements note)

## How to Use
1. Read `Project_Requirements.md` to confirm the target requirements.
2. Use `Project_Plan.md` as the roadmap and ensure every major task references the applicable requirement IDs.
3. When making code changes, link implementation details back to requirements (e.g., “implements FR-PROD-002 search endpoint”).
4. Update this skill file if requirement mappings change or new requirement IDs are added.

## Key Outputs
- `Project_Plan.md` (the detailed roadmap with milestones and tasks)
- Requirement-to-feature mapping tables or checklists (to track coverage)
- Suggested development approach for each major requirement area

## Notes
- This skill is focused on planning and alignment; actual code changes happen in `backend/` and `website-project/`.
- Use tools to inspect current code (routes/controllers/components) and validate what requirements are already satisfied.
