# Hirecentic
CampusPilot AI is a placement intelligence platform for IMSEC and similar colleges, simplifying student management, placement drive tracking, and automated eligibility-based shortlisting using React, Tailwind CSS, and Supabase.
## 1. Executive Summary
CampusPilot AI is a proposed placement-intelligence platform for Career Development Centres (CDCs), placement offices,
students and recruiters. It unifies student profiles, skills evidence, employer requirements, eligibility rules, recruitment workflows,
personalized preparation and placement analytics.
Its goal is not simply to rank students. It aims to make placement operations more efficient and transparent while helping students
become ready for suitable opportunities. Mandatory eligibility is kept separate from role-specific matching, recommendations are
explainable, and final shortlist decisions remain with authorized humans.
Recommended delivery: a focused 10–12 week MVP for one institution or selected cohort, followed by a controlled pilot and phased
expansion toward multi-college SaaS. Start with a modular monolith, deterministic matching and targeted AI assistance—not
premature microservices or an opaque hiring-prediction model.
## 2. Vision, Mission and Value Proposition
Vision
Become a trusted placement-intelligence layer connecting student capabilities with employer needs while helping institutions
continuously improve career readiness.
Mission
Unify placement data, make matching explainable, reduce repetitive CDC work, and give students practical, evidence-led routes
toward suitable roles.
Value by stakeholder
• CDC / placement officers: centralized records, configurable eligibility, explainable shortlists, drive operations, alerts and outcome
analytics.
• Students: a skills portfolio, role discovery, evidence-backed readiness feedback and personalized improvement roadmaps.
• Recruiters: consistent candidate summaries, role-specific evidence and controlled recruitment coordination.
• College leadership: cohort-level trends, conversion bottlenecks, program impact and more reliable reporting.
Product principles
• Evidence before inference: distinguish verified, imported and self-reported claims.
• Eligibility before ranking: mandatory rules and suitability scores remain separate.
• Support, do not stigmatize: readiness is role-specific and changeable, not a permanent label.
• Human accountability: authorized staff review shortlists and exceptions; AI does not make final hiring decisions.
• Privacy by design: least privilege, institution-level isolation, data minimization and auditability.
• Measurable value: compare operational and placement outcomes with a baseline; do not promise unverified placement increases.
## 3. Problem Statement and Opportunity
Placement operations can span spreadsheets, email, forms, resumes, coding profiles, assessment results and separate
company-drive trackers. Fragmentation can cause duplicated data entry, inconsistent eligibility checks, weak visibility into student
readiness, delayed communication and limited insight into where candidates drop out.
Students may struggle to understand why they were not shortlisted, which evidence employers value, which roles suit their
demonstrated strengths, and what to do next. A single CGPA or generic readiness score cannot capture the requirements of every
role.
Problems to validate
• Fragmented student records and repeated data cleaning.
• Time-consuming eligibility filtering and shortlist preparation.
• Inconsistent verification of resumes, projects and coding activity.
• Poor role-specific mapping between student evidence and employer requirements.
• Limited personalized guidance after a missed shortlist or assessment.
• Drive scheduling, deadlines, document collection and stage tracking across disconnected tools.
• Insufficient funnel analytics to identify drop-off points.
• Difficulty measuring the impact of training and mock interviews.
• Limited auditability of criteria, overrides and changes to employer requirements.
Page 3
CampusPilot AI • Project Specification • v1.0
CampusPilot AI • Project Specification • v1.0 Page 4
These are hypotheses, not claims about every college. Interview CDC staff, faculty coordinators, students and recruiters to validate
the highest-value problems.
## 4. Objectives and Success Criteria
Primary objectives
• Create a single source of truth for student placement profiles and evidence.
• Make company-specific eligibility filtering repeatable and auditable.
• Generate explainable role-specific candidate matches.
• Provide actionable skill-gap plans to students.
• Track recruitment from drive creation through offer and joining.
• Give CDC staff reliable operational and outcome analytics.
• Build a secure architecture that can support multiple institutions.
Proposed pilot KPIs
KPI Measurement Provisional pilot target
Shortlist preparation time Median staff time for comparable
shortlists
30% reduction vs. baseline
Profile completeness Invited students completing required
fields/evidence
85%
Import quality Valid records accepted without
correction after iteration
95%
Matching explainability Matches with score components and
evidence links
100%
Workflow traceability Critical actions with actor, timestamp
and reason
100%
Student actionability Active users completing one
recommended task
Measure baseline; aim for 50%
Rule correctness Release-blocking eligibility/scoring
tests passing
100%
Placement conversion Stage conversion and final outcomes Establish baseline; avoid guaranteed uplift
Targets are starting hypotheses. Revise them with the pilot sponsor after baseline measurement. Do not attribute placement
conversion changes to the platform without considering other factors and, where possible, an appropriate comparison.
## 5. Users, Roles and Permissions
Role Core permissions Safeguards
Platform Super Admin Provision institutions; manage platform
configuration and service health
No routine student-record browsing; elevated access logged and justified
Institution Admin Manage institution settings, staff
memberships and policy configuration
Limited to own institution
CDC / Placement Officer Import records, configure drives/rules,
review matches, manage
stages/outcomes
Sensitive actions audited; humans own final decisions
Faculty / Coordinator View assigned cohort and track
preparation
Only assigned cohorts and permitted fields
Student Manage own profile, evidence,
applications, plans and corrections
Cannot access another student's private records
Recruiter View authorized candidate information
for assigned drives
Only approved fields/candidates; time-bounded access
Leadership / Auditor View permitted reports and audit
summaries
Read-only; aggregated views by default
Use role-based access control (RBAC) plus institution- and resource-level authorization. Every sensitive action must be checked on
the backend, not merely hidden in the frontend.
## 6. Product Scope and Feature Modules
Module 1 — Institution and access management
• Institution provisioning and tenant configuration.
• User invitations, roles, account lifecycle and secure authentication.
• Departments, programs, batches, graduating years and placement policies.
• Audit events for permission changes and sensitive operations.
Module 2 — Student master data and imports
• CSV/XLSX import with field mapping, validation, duplicate detection and downloadable error reports.
• Student identifiers, program, branch, graduation year, CGPA and approved eligibility attributes.
• Import preview, explicit confirmation, rollback strategy and import history.
• Profile-completion status and correction workflow.
Module 3 — Student profile and evidence portfolio
• Resume upload and structured extraction with student correction.
• Projects with contribution, stack, repository/demo links and review status.
• Coding-platform URLs and permitted metrics with source and last-verified timestamp.
• Certifications, internships, assessments and skills with evidence provenance.
• Separate verified, imported, expired and self-reported claims.
Module 4 — Assessment and skill catalogue
• Standard skill taxonomy across programming, DSA, databases, web, cloud, AI and CS fundamentals.
• Assessment definitions, rubric, scores, date, assessor, freshness and attempt history.
• Optional college-created quizzes, practical tasks, coding assessments and mock interviews.
• Integrity signals are review aids, not automatic fraud findings.
Module 5 — Company, role and drive management
• Employer profiles and authorized contacts.
• Job/role descriptions, skills, location, compensation details and selection stages.
• Drive calendar, application windows, deadlines, documents, communications and seat counts.
• Versioned employer criteria; approval before changes affect an active drive.
Module 6 — Eligibility and matching engine
• Configurable hard filters for employer-defined mandatory criteria.
• Role-specific weighted score across relevant skills, assessments, technical evidence, projects and experience.
• Missing-data indicators, score explanations, evidence links and coverage/freshness display.
• Filterable, sortable and reproducible results with tie-handling.
• Human review, override reason, scoring version and audit trail.
• No hidden blanket cutoff or use of sensitive/protected attributes as ranking features.
Module 7 — Student career-readiness workspace
• Role-family recommendations based on evidence and stated goals.
• Skill-gap breakdown against target job requirements.
• Prioritized 30/60/90-day preparation plans and milestones.
• Recommended practice, project improvements, resume revisions and mock interviews.
• Progress based on completed tasks and fresh evidence—not promises of hiring or salary.
Module 8 — Placement-drive workflow
• Application and interest capture where appropriate.
• Eligibility confirmation and shortlist review.
• Assessment, interview stage, attendance, result, offer, acceptance and joining status.
• Notifications for deadlines, missing documents, conflicts and status changes.
• Configurable institution policies for multiple offers and drive participation.
Page 5
CampusPilot AI • Project Specification • v1.0
Module 9 — Analytics and reports
• Recruitment funnel: eligible, applied, shortlisted, assessed, interviewed, offered, accepted and joined.
• Conversion by cohort, branch, role family, employer, drive and stage, subject to permissions and privacy safeguards.
• Profile completeness, skill gaps, assessment participation and training progress.
• Exportable reports and scheduled summaries with definitions and data freshness labels.
• Historical comparison with careful interpretation; correlation is not proof of causation.
Module 10 — CDC Copilot
• Natural-language questions answered from authorized structured data.
• Example: 'Which eligible students have verified Python assessment results but lack a data project?'
• Answers show filters, definitions, counts and evidence/source links.
• Use read-only query tools or controlled APIs; no arbitrary SQL, cross-tenant access or unreviewed write actions.
• AI summaries are labelled and checked against underlying records.
Module 11 — Notifications and task automation
• Email/in-app notifications for deadlines, invitations, profile completion and drive changes.
• Background jobs for file parsing, bulk imports and reports.
• Retry handling, delivery status, user preferences and duplicate suppression.
Module 12 — Administration, audit and governance
• Audit logs for criteria changes, shortlist generation, exports, overrides, permissions and offer edits.
• Data retention, correction, export and deletion workflows based on institutional policy and applicable law.
• Institution-specific policies and consent/notice flows.
• Operational dashboards for failures, queues, integrations and security events.
## 7. Matching Methodology and Opportunity Guidance
Do not assign a universal salary or permanent tier to a student. Compute fit for a specific role and show suitable opportunities with
evidence and gaps. Compensation is an employer/job attribute, not a guaranteed consequence of a student score.
Recommended two-stage approach
• Stage A — Eligibility: apply only explicit, approved mandatory conditions; record each rule and result.
• Stage B — Suitability: rank eligible candidates using a role-specific, configurable rubric based on job-related evidence.
• Stage C — Review: show rationale, missing evidence, freshness and data-quality concerns for CDC review.
• Stage D — Learning loop: turn gaps into tasks; recalculate when evidence or approved criteria change.
Illustrative initial scoring rubric
Dimension
Starting weight
Evidence examples
Coding and DSA
Role-relevant technical skills
25%
20%
Standardized assessments; permitted platform evidence
Practical tests, projects and verified assessments
Project quality and implementation
20%
Repository, deployment, documented contribution, review rubric
Resume and relevant experience
10%
Internship/project evidence; student-corrected extraction
CS fundamentals
Communication/interview readiness
10%
10%
Structured assessment or interview rubric
Consistent, job-relevant rubric and practice feedback
Coding-platform activity
5%
Permitted, current and contextualized activity
Weights are experimental defaults, not validated predictive weights. Configure them per role and review for unintended effects.
Avoid double-counting the same project. Show missing evidence separately from poor performance; absence of a public profile
must not imply lack of ability.
Opportunity bands
Use descriptive categories such as 'foundation-building opportunities', 'core software roles' and 'advanced/specialist opportunities'
only as navigation aids. Show actual advertised compensation, role requirements and evidence-based fit where available. Do not
promise package outcomes or infer salary from a score.
Page 6
CampusPilot AI • Project Specification • v1.0
## 8. Technical Architecture and Stack
Recommended approach: a modular monolith with clear domain boundaries and one backend deployment initially. It is easier to
build and operate than microservices while leaving room to extract components when real load or team ownership justifies it.
Layer
Recommended technology
Responsibility
Frontend
UI
Next.js + TypeScript
Tailwind CSS + accessible component
library
Student, CDC, institution admin and recruiter interfaces
Responsive, consistent UI
Backend API
Database
Python + FastAPI + Pydantic
PostgreSQL
Validation, domain logic, REST API and OpenAPI docs
Transactional source of truth and reporting
ORM/migrations
Authentication
SQLAlchemy + Alembic
Managed identity or secure
session/JWT design
Data access and versioned schema
Login, sessions, roles and resource authorization
AI integration
Matching
LLM API with structured
outputs/schema validation
Resume extraction, summaries, coaching
Versioned deterministic scoring service Reproducible eligibility and role-fit calculations
File storage
Background work
Private S3-compatible object storage
Redis + task worker when needed
Resumes, certificates and attachments
Parsing, imports, notifications and reports
Testing
Delivery
Pytest, frontend unit tests, Playwright
Docker, CI/CD, managed cloud
platform
Unit, API, integration and browser tests
Repeatable deployment and automated checks
Observability
High-level flow
Structured logs, metrics and error
reporting
Reliability, troubleshooting and alerting
Browser UI fi authenticated API fi domain modules fi PostgreSQL / private object storage / approved external services.
Long-running tasks are queued and processed asynchronously. AI services receive the minimum required data and never bypass
application authorization.
Core domain boundaries
• Identity and tenancy
• Student profile and evidence
• Assessment and skill taxonomy
• Employer, job role and drive
• Eligibility and matching
• Career development plans
• Recruitment stages and offers
• Analytics and reporting
• Notifications and integrations
• Audit and governance
Do not start with Kubernetes, a large event bus or microservices. Add infrastructure only when measurable needs justify the

