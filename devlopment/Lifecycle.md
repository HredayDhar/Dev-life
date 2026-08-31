# Senior Software Engineering Workflow

> A production-grade workflow for planning, designing, developing, testing, deploying, and maintaining software.

---

# Table of Contents

1. [Engineering Mindset](#1-engineering-mindset)
2. [Complete Development Lifecycle](#2-complete-development-lifecycle)
3. [Phase 0 — Project Intake](#3-phase-0--project-intake)
4. [Phase 1 — Problem Definition](#4-phase-1--problem-definition)
5. [Phase 2 — Requirements](#5-phase-2--requirements)
6. [Phase 3 — Scope](#6-phase-3--scope)
7. [Phase 4 — Stakeholders](#7-phase-4--stakeholders)
8. [Phase 5 — User Personas](#8-phase-5--user-personas)
9. [Phase 6 — User Stories](#9-phase-6--user-stories)
10. [Phase 7 — Use Cases](#10-phase-7--use-cases)
11. [Phase 8 — Functional Requirements](#11-phase-8--functional-requirements)
12. [Phase 9 — Non-Functional Requirements](#12-phase-9--non-functional-requirements)
13. [Phase 10 — Constraints & Assumptions](#13-phase-10--constraints--assumptions)
14. [Phase 11 — Risks](#14-phase-11--risks)
15. [Phase 12 — Technical Feasibility](#15-phase-12--technical-feasibility)
16. [Phase 13 — Technology Selection](#16-phase-13--technology-selection)
17. [Phase 14 — System Design](#17-phase-14--system-design)
18. [Phase 15 — Architecture](#18-phase-15--architecture)
19. [Phase 16 — Database Design](#19-phase-16--database-design)
20. [Phase 17 — API Design](#20-phase-17--api-design)
21. [Phase 18 — Security Design](#21-phase-18--security-design)
22. [Phase 19 — UI/UX Design](#22-phase-19--uiux-design)
23. [Phase 20 — Project Structure](#23-phase-20--project-structure)
24. [Phase 21 — Development Plan](#24-phase-21--development-plan)
25. [Phase 22 — Definition of Done](#25-phase-22--definition-of-done)
26. [Phase 23 — Development](#26-phase-23--development)
27. [Phase 24 — Git Workflow](#27-phase-24--git-workflow)
28. [Phase 25 — Testing](#28-phase-25--testing)
29. [Phase 26 — Security Testing](#29-phase-26--security-testing)
30. [Phase 27 — Performance Testing](#30-phase-27--performance-testing)
31. [Phase 28 — Code Review](#31-phase-28--code-review)
32. [Phase 29 — Documentation](#32-phase-29--documentation)
33. [Phase 30 — CI/CD](#33-phase-30--cicd)
34. [Phase 31 — Environment Management](#34-phase-31--environment-management)
35. [Phase 32 — Staging](#35-phase-32--staging)
36. [Phase 33 — Production Deployment](#36-phase-33--production-deployment)
37. [Phase 34 — Monitoring & Observability](#37-phase-34--monitoring--observability)
38. [Phase 35 — Incident Management](#38-phase-35--incident-management)
39. [Phase 36 — Post-Release](#39-phase-36--post-release)
40. [Phase 37 — Technical Debt](#40-phase-37--technical-debt)
41. [Phase 38 — Maintenance](#41-phase-38--maintenance)
42. [Phase 39 — Refactoring](#42-phase-39--refactoring)
43. [Phase 40 — Product Feedback](#43-phase-40--product-feedback)
44. [Phase 41 — Project Retrospective](#44-phase-41--project-retrospective)
45. [Engineering Checklists](#45-engineering-checklists)
46. [Project Documentation Structure](#46-project-documentation-structure)
47. [Senior Engineer Questions](#47-senior-engineer-questions)
48. [Final Production Checklist](#48-final-production-checklist)

---

# 1. Engineering Mindset

A senior developer does not begin with:

> "What code should I write?"

They begin with:

> "What problem are we solving, for whom, and what is the safest and simplest way to solve it?"

The engineering mindset is:

```text
Problem
   ↓
Requirements
   ↓
Scope
   ↓
Risks
   ↓
Design
   ↓
Plan
   ↓
Implementation
   ↓
Testing
   ↓
Review
   ↓
Deployment
   ↓
Monitoring
   ↓
Feedback
   ↓
Improvement
```

## Core principles

### 1. Understand before implementing

Do not start coding when requirements are unclear.

### 2. Prefer simplicity

Do not introduce:

* Microservices
* Kubernetes
* Redis
* Message queues
* Event-driven architecture
* AI
* Complex caching

unless there is a real requirement.

### 3. Design for change

Requirements will change.

Structure the system so changes are localized.

### 4. Security is part of engineering

Security is not a final step.

### 5. Testing is part of development

Testing should be planned before implementation.

### 6. Production is part of development

A feature is not complete simply because it works locally.

### 7. Measure instead of guessing

Use:

* Logs
* Metrics
* Traces
* User feedback
* Performance measurements
* Business metrics

### 8. Document important decisions

Future developers need to understand:

> "Why was this decision made?"

---

# 2. Complete Development Lifecycle

```text
PHASE A — DISCOVERY

1. Project Intake
2. Problem Definition
3. Requirements
4. Stakeholders
5. User Personas
6. User Stories
7. Use Cases
8. Scope
9. Constraints
10. Assumptions
11. Risks
12. Feasibility


PHASE B — DESIGN

13. Technology Selection
14. System Design
15. Architecture
16. Database Design
17. API Design
18. Security Design
19. UI/UX Design
20. Project Structure


PHASE C — PLANNING

21. Development Plan
22. Task Breakdown
23. Prioritization
24. Definition of Done
25. Release Plan


PHASE D — IMPLEMENTATION

26. Development
27. Git Workflow
28. Unit Testing
29. Integration Testing
30. Code Review


PHASE E — VALIDATION

31. Security Testing
32. Performance Testing
33. E2E Testing
34. QA
35. Documentation


PHASE F — DELIVERY

36. CI/CD
37. Environment Setup
38. Staging
39. Production Deployment


PHASE G — OPERATIONS

40. Monitoring
41. Logging
42. Alerting
43. Incident Management
44. Backup & Recovery


PHASE H — IMPROVEMENT

45. User Feedback
46. Analytics
47. Technical Debt
48. Refactoring
49. Retrospective
50. Roadmap
```

---

# 3. Phase 0 — Project Intake

Before starting, collect the initial information.

## Project information

```text
Project Name:
Project Owner:
Team:
Start Date:
Target Release:
Expected Users:
Platform:
Budget:
Deadline:
```

## Initial questions

* What are we building?
* Why are we building it?
* Who will use it?
* What business problem does it solve?
* What is the expected result?
* What is the deadline?
* What constraints exist?
* What already exists?
* What must integrate with external systems?

---

# 4. Phase 1 — Problem Definition

Never begin with technology.

Begin with the problem.

## Problem Statement

Use:

```text
[Target user] currently has [problem].

This causes [negative impact].

We want to solve this by [high-level solution].

Success means [measurable outcome].
```

## Example

```text
Small retailers currently manage inventory manually.

This causes inaccurate stock counts, lost sales,
and difficulty tracking transactions.

We want to provide a centralized inventory system.

Success means users can accurately track stock,
sales, and product movement.
```

## Questions

* What problem exists?
* Who experiences it?
* How frequently?
* How severe is it?
* What is the current workaround?
* Why is the current solution insufficient?
* What does success look like?

---

# 5. Phase 2 — Requirements

Requirements describe what the system must accomplish.

## Requirement categories

```text
Business Requirements
Functional Requirements
Non-Functional Requirements
Technical Requirements
Security Requirements
Compliance Requirements
Operational Requirements
```

## Requirements should be

```text
Specific
Measurable
Testable
Unambiguous
Traceable
Prioritized
```

---

# 6. Phase 3 — Scope

Define what is included and excluded.

## MVP

```text
Must Have
```

## Phase 2

```text
Should Have
```

## Future

```text
Could Have
```

## Out of Scope

```text
Explicitly not building.
```

## Example

```text
MVP:
✓ Authentication
✓ Product management
✓ Inventory
✓ Sales

Phase 2:
○ Notifications
○ Analytics
○ Advanced reports

Future:
○ AI recommendations

Out of Scope:
× Social network
× Blockchain
× Cryptocurrency payments
```

---

# 7. Phase 4 — Stakeholders

Identify stakeholders.

```text
Customer
Admin
Manager
Employee
Business Owner
Developer
Designer
QA
DevOps
Security
External API Provider
Payment Provider
```

For every stakeholder:

```text
What do they need?
What can they do?
What information do they access?
What can they change?
What risks affect them?
```

---

# 8. Phase 5 — User Personas

Define major users.

Example:

```text
Persona: Shop Owner

Goals:
- Track inventory
- Track sales
- Monitor business

Problems:
- Manual records
- Inventory mistakes
- Difficult reporting

Technical skill:
Medium

Primary device:
Mobile
```

---

# 9. Phase 6 — User Stories

Format:

```text
As a [user],
I want [action],
so that [benefit].
```

Example:

```text
As a shop owner,
I want to add a product,
so that I can track it in inventory.
```

## Acceptance Criteria

```text
Given:
The user is authenticated.

When:
The user creates a valid product.

Then:
The product is saved.

And:
The product appears in inventory.
```

---

# 10. Phase 7 — Use Cases

Describe complete interactions.

## Example

### Use Case: Create Product

```text
Actor:
Shop Owner

Precondition:
User is authenticated.

Main Flow:
1. User opens inventory.
2. User selects Add Product.
3. User enters product information.
4. System validates information.
5. System saves product.
6. System displays success.

Alternative Flow:
Invalid information.

System:
Displays validation errors.

Failure Flow:
Database unavailable.

System:
Displays retry message.
Logs the failure.
```

---

# 11. Phase 8 — Functional Requirements

Functional requirements describe system behavior.

Example:

```text
FR-001
The system shall allow users to register.

FR-002
The system shall allow authenticated users to log in.

FR-003
The system shall allow authorized users to create products.

FR-004
The system shall prevent unauthorized users
from modifying products.
```

Every requirement should ideally be testable.

---

# 12. Phase 9 — Non-Functional Requirements

Define system quality attributes.

## Performance

```text
API response target:
< 500 ms for normal requests
```

## Availability

```text
Target:
99.9%
```

## Scalability

Define expected:

```text
Users
Requests/second
Database size
File storage
Traffic
```

## Security

```text
Authentication
Authorization
Encryption
Secrets
Audit logs
Rate limiting
```

## Reliability

```text
Retries
Timeouts
Failure handling
Backups
Recovery
```

## Maintainability

```text
Modular architecture
Tests
Documentation
Code standards
```

---

# 13. Phase 10 — Constraints & Assumptions

## Constraints

Examples:

```text
Limited budget
Small development team
Fixed deadline
Existing infrastructure
Third-party API limitations
Device limitations
Legal requirements
```

## Assumptions

Examples:

```text
Users have internet access.
Users have smartphones.
External API remains available.
Payment provider supports required operations.
```

Track assumptions because incorrect assumptions can invalidate designs.

---

# 14. Phase 11 — Risks

Create a risk register.

| ID    | Risk                   | Probability |   Impact | Mitigation            |
| ----- | ---------------------- | ----------: | -------: | --------------------- |
| R-001 | Payment API failure    |      Medium |     High | Retry + fallback      |
| R-002 | Database overload      |         Low |     High | Indexing + monitoring |
| R-003 | Security vulnerability |      Medium | Critical | Security testing      |
| R-004 | Deadline delay         |      Medium |   Medium | MVP prioritization    |

## Risk categories

```text
Technical
Security
Financial
Operational
Legal
Product
Performance
Scalability
Third-party dependencies
```

---

# 15. Phase 12 — Technical Feasibility

Before implementation, determine whether the proposed system is technically realistic.

Ask:

```text
Can we build it?

Can the selected technology support it?

Can the infrastructure support expected traffic?

Can the database handle expected data?

Can external APIs support required functionality?

Can we secure it?

Can we maintain it?

Can we afford it?
```

If there is uncertainty:

```text
Create Proof of Concept
```

Do not spend weeks building a system around an unverified assumption.

---

# 16. Phase 13 — Technology Selection

Choose technology based on requirements.

Evaluate:

```text
Performance
Developer productivity
Community
Maturity
Security
Cost
Scalability
Maintenance
Team expertise
Hiring availability
Ecosystem
Vendor lock-in
```

## Example

```text
Frontend:
Flutter

Backend:
TypeScript

Database:
PostgreSQL

Cache:
Redis only if required

Storage:
Object storage

CI/CD:
GitHub Actions

Containerization:
Docker
```

Technology should serve the system—not the other way around.

---

# 17. Phase 14 — System Design

System design answers:

> "How will the parts of this system work together?"

Create:

```text
High-Level Architecture
Component Diagram
Data Flow
Sequence Diagrams
Deployment Architecture
Failure Scenarios
Security Boundaries
```

---

# 18. Phase 15 — Architecture

## Architecture responsibilities

Each component should have a clear responsibility.

Example:

```text
Client
   ↓
API
   ↓
Application Layer
   ↓
Domain Layer
   ↓
Data Layer
   ↓
Database
```

Avoid:

```text
Everything inside one giant class/file.
```

---

# 19. Phase 16 — Database Design

Design the data model before implementation.

## Define

```text
Entities
Relationships
Primary Keys
Foreign Keys
Indexes
Constraints
Transactions
Audit History
Soft Delete
Data Retention
```

Example:

```text
User
 ├── id
 ├── name
 ├── email
 └── created_at

Product
 ├── id
 ├── name
 ├── category_id
 ├── price
 └── created_at

Sale
 ├── id
 ├── customer_id
 ├── product_id
 ├── amount
 └── created_at
```

## Database questions

* What happens when data is deleted?
* Which fields require indexes?
* What data must be unique?
* What operations require transactions?
* How will migrations work?
* How will backups work?
* How will historical data be retained?

---

# 20. Phase 17 — API Design

Define API contracts.

Example:

```http
POST   /api/v1/products
GET    /api/v1/products
GET    /api/v1/products/:id
PATCH  /api/v1/products/:id
DELETE /api/v1/products/:id
```

Define:

```text
Request
Response
Validation
Authentication
Authorization
Errors
Pagination
Filtering
Sorting
Rate Limits
Versioning
```

## Error format

Use a consistent structure.

```json
{
  "success": false,
  "error": {
    "code": "PRODUCT_NOT_FOUND",
    "message": "Product was not found"
  }
}
```

---

# 21. Phase 18 — Security Design

Security must be designed before implementation.

## Authentication

```text
How does a user prove identity?
```

## Authorization

```text
What can each role access?
```

Example:

```text
Admin
 ├── Users
 ├── Products
 ├── Reports
 └── Settings

Employee
 ├── Products
 └── Sales
```

## Security checklist

```text
✓ Authentication
✓ Authorization
✓ RBAC
✓ Input validation
✓ Output encoding
✓ Secure password handling
✓ Session management
✓ Token expiration
✓ Rate limiting
✓ Secrets management
✓ Encryption
✓ Audit logs
✓ Secure file uploads
✓ Dependency security
✓ API security
```

## Threat modeling

Ask:

```text
What can go wrong?

Who could attack the system?

What assets are valuable?

What happens if an attacker controls input?

What happens if authentication is bypassed?

What happens if an API is abused?

What happens if the database is compromised?
```

---

# 22. Phase 19 — UI/UX Design

Create user flows before implementation.

Example:

```text
Login
 ↓
Dashboard
 ↓
Inventory
 ↓
Product Details
 ↓
Sell Product
 ↓
Payment
 ↓
Receipt
```

Every screen should define:

```text
Normal State
Loading State
Empty State
Error State
Success State
Offline State
Permission State
Validation State
```

Do not design only the happy path.

---

# 23. Phase 20 — Project Structure

Define the codebase structure before it becomes large.

Example:

```text
src/
├── core/
│   ├── config/
│   ├── constants/
│   ├── errors/
│   ├── network/
│   ├── security/
│   └── utils/
│
├── features/
│   ├── auth/
│   ├── users/
│   ├── inventory/
│   ├── sales/
│   └── reports/
│
├── shared/
│   ├── components/
│   └── models/
│
└── main/
```

Architecture should make it easy to answer:

> "Where should this code live?"

---

# 24. Phase 21 — Development Plan

Break large requirements into small tasks.

Bad:

```text
Build authentication.
```

Better:

```text
AUTH-001 Create user model
AUTH-002 Create validation
AUTH-003 Create registration API
AUTH-004 Create login API
AUTH-005 Create auth repository
AUTH-006 Create auth state management
AUTH-007 Create login UI
AUTH-008 Create registration UI
AUTH-009 Handle errors
AUTH-010 Add tests
```

## Task structure

```text
Task ID
Title
Description
Dependencies
Acceptance Criteria
Estimated Effort
Priority
Status
```

---

# 25. Phase 22 — Definition of Done

A feature is not complete because the code compiles.

Example:

```text
Feature is DONE when:

✓ Requirements implemented
✓ UI implemented
✓ Validation implemented
✓ Error handling implemented
✓ Unit tests written
✓ Integration tests written where necessary
✓ Security reviewed
✓ Code reviewed
✓ Documentation updated
✓ CI passes
✓ No critical bugs
✓ Acceptance criteria satisfied
```

---

# 26. Phase 23 — Development

Now start coding.

Recommended cycle:

```text
Understand
   ↓
Design
   ↓
Implement
   ↓
Test
   ↓
Review
   ↓
Refactor
   ↓
Commit
```

## During implementation

Keep asking:

```text
Is this the simplest solution?

Is the responsibility clear?

Can this fail?

Is the error handled?

Is the input validated?

Is authorization enforced?

Is this testable?

Will future developers understand it?
```

---

# 27. Phase 24 — Git Workflow

Use meaningful branches.

```text
main
develop
feature/*
fix/*
hotfix/*
release/*
```

Example:

```text
feature/inventory-product-creation
fix/payment-timeout
hotfix/auth-token-expiry
```

## Commit messages

Good:

```text
feat(auth): add email login
feat(inventory): add product creation
fix(payment): handle timeout
test(auth): add login tests
refactor(inventory): extract product validator
docs(api): document product endpoints
```

Avoid:

```text
update
changes
final
final2
new
working
asdf
```

---

# 28. Phase 25 — Testing

Testing strategy:

```text
              E2E
               ↑
          Integration
               ↑
              Unit
```

## Unit Testing

Test individual components.

Examples:

```text
Validators
Calculations
Business rules
Utilities
Services
```

## Integration Testing

Test:

```text
API + Database
Authentication + Database
Payment + Backend
Repository + Database
```

## E2E Testing

Test real user journeys.

Example:

```text
Register
 ↓
Login
 ↓
Create Product
 ↓
Create Sale
 ↓
Payment
 ↓
Receipt
```

---

# 29. Phase 26 — Security Testing

Security testing evaluates the system's ability to protect data and maintain functionality under malicious conditions. It goes beyond functional testing to identify vulnerabilities, threats, and risks that could lead to unauthorized access, data breaches, or system compromise.

## Security Testing Methodologies

Refer to the detailed security testing materials in `34-SECURITY-TESTING/` for comprehensive guidance on:

1. **Security Test Planning** (`01-SECURITY-TEST-PLANNING.md`) - Define objectives, scope, methodologies, and resources
2. **Authentication Testing** (`02-AUTHENTICATION-TESTING.md`) - Verify identity verification mechanisms
3. **Authorization Testing** (`03-AUTHORIZATION-TESTING.md`) - Validate access control and permission systems
4. **Input Testing** (`04-INPUT-TESTING.md`) - Test validation and sanitization of all external inputs
5. **Dependency Scanning** (`05-DEPENDENCY-SCANNING.md`) - Identify vulnerabilities in third-party components
6. **Secrets Scanning** (`06-SECRETS-SCANNING.md`) - Detect exposed credentials and sensitive data
7. **Penetration Testing** (`07-PENETRATION-TESTING.md`) - Conduct authorized simulated attacks to evaluate security posture

## Key Areas to Check

During security testing, verify the following common vulnerability categories:

```text
Authentication bypass
Authorization problems
IDOR (Insecure Direct Object Reference)
Injection (SQL, NoSQL, Command, etc.)
XSS (Cross-Site Scripting)
CSRF (Cross-Site Request Forgery)
Broken access control
Sensitive data exposure
Weak passwords
Improper session handling
Rate-limit bypass
File upload vulnerabilities
Exposed secrets
Insecure dependencies
```

## Best Practices

- Only test systems you are explicitly authorized to test
- Follow established methodologies (OWASP, NIST, PTES)
- Combine automated scanning with manual testing
- Test both known vulnerabilities and business logic flaws
- Validate findings to avoid false positives
- Report vulnerabilities with clear remediation guidance
- Retest fixes to ensure proper resolution
- Integrate security testing throughout the SDLC, not just as a phase

---

# 30. Phase 27 — Performance Testing

Measure instead of guessing.

Test:

```text
Response time
Throughput
Concurrent users
Database performance
Memory
CPU
Network
File operations
```

Find:

```text
Slow queries
N+1 queries
Unnecessary API calls
Large payloads
Memory leaks
Expensive computations
```

Optimize only after measuring.

---

# 31. Phase 28 — Code Review

Review:

## Correctness

Does it actually solve the requirement?

## Architecture

Does it belong here?

## Security

Can it be abused?

## Performance

Is there an obvious bottleneck?

## Maintainability

Will future developers understand it?

## Testing

Are important cases covered?

## Simplicity

Can the same result be achieved more simply?

---

# 32. Phase 29 — Documentation

At minimum:

```text
README.md
ARCHITECTURE.md
API.md
DATABASE.md
SECURITY.md
DEPLOYMENT.md
CONTRIBUTING.md
CHANGELOG.md
```

Document important decisions.

Example:

```text
ADR-001: Use PostgreSQL

Context:
The application requires relational data and transactions.

Decision:
Use PostgreSQL.

Reason:
Strong relational constraints and transaction support.

Alternatives:
MongoDB

Rejected because:
Relational consistency is more important for this system.
```

---

# 33. Phase 30 — CI/CD

Automate quality checks.

```text
Git Push
   ↓
Lint
   ↓
Format Check
   ↓
Unit Tests
   ↓
Integration Tests
   ↓
Security Scan
   ↓
Build
   ↓
Deploy Staging
   ↓
Approval
   ↓
Production
```

CI should prevent broken code from reaching production.

---

# 34. Phase 31 — Environment Management

Use separate environments.

```text
Local
Development
Staging
Production
```

Never hardcode:

```text
API keys
Passwords
Database credentials
Private keys
Tokens
Secrets
```

Use environment variables or a proper secrets manager.

---

# 35. Phase 32 — Staging

Staging should resemble production as closely as practical.

Verify:

```text
Authentication
Database
API
UI
Payments
Notifications
File uploads
Permissions
Performance
Error handling
```

Run smoke tests before production.

---

# 36. Phase 33 — Production Deployment

Before deployment:

```text
✓ Backup completed
✓ Migration tested
✓ Environment verified
✓ Secrets configured
✓ Monitoring enabled
✓ Logging enabled
✓ Health checks enabled
✓ Rollback plan prepared
✓ Deployment owner assigned
```

## Rollback plan

Always know:

> "How do we return to the previous working version?"

---

# 37. Phase 34 — Monitoring & Observability

Production requires visibility.

Monitor:

```text
Logs
Metrics
Traces
Errors
Latency
Availability
CPU
Memory
Database
Traffic
Queue depth
Business metrics
```

## Health checks

Example:

```http
GET /health
```

Possible response:

```json
{
  "status": "healthy"
}
```

---

# 38. Phase 35 — Incident Management

When production fails:

```text
Detect
 ↓
Investigate
 ↓
Contain
 ↓
Recover
 ↓
Communicate
 ↓
Root Cause Analysis
 ↓
Fix
 ↓
Prevent Recurrence
```

Do not only fix the immediate bug.

Ask:

> Why did the system allow this failure?

---

# 39. Phase 36 — Post-Release

After release, measure:

```text
Crash rate
Error rate
Performance
User adoption
Conversion
Retention
Feature usage
Support tickets
```

Compare actual results with expected results.

---

# 40. Phase 37 — Technical Debt

Technical debt is normal.

The mistake is ignoring it.

Track it.

Example:

```text
TECH-001
Refactor duplicated validation.

TECH-002
Add missing database indexes.

TECH-003
Improve test coverage.

TECH-004
Replace temporary authentication implementation.
```

Prioritize debt based on:

```text
Risk
Cost
Frequency
Business impact
Security impact
```

---

# 41. Phase 38 — Maintenance

Software requires continuous maintenance.

Regularly review:

```text
Dependencies
Security patches
Database health
Infrastructure
Logs
Performance
Backups
Certificates
API versions
Third-party integrations
```

---

# 42. Phase 39 — Refactoring

Refactor when there is a reason.

Good reasons:

```text
Repeated code
Complex logic
Poor boundaries
Performance issue
Security issue
Hard-to-test code
Frequent changes
```

Avoid refactoring purely because:

> "I don't like how it looks."

Refactoring should reduce future cost or risk.

---

# 43. Phase 40 — Product Feedback

Engineering isn't isolated from users.

Collect:

```text
User feedback
Bug reports
Support tickets
Analytics
Feature requests
Usage patterns
```

Then prioritize.

A feature that users don't need should not automatically receive engineering resources.

---

# 44. Phase 41 — Project Retrospective

At the end of a major release, ask:

## What went well?

```text
What worked?
```

## What went badly?

```text
What caused problems?
```

## Why?

Find root causes.

## What should change?

Create actionable improvements.

Example:

```text
Problem:
Database migration caused staging failure.

Root cause:
Migration was not tested against production-like data.

Action:
Add migration testing to CI.
```

---

# 45. Engineering Checklists

# Pre-Development Checklist

```text
[ ] Problem understood
[ ] Business objective defined
[ ] Stakeholders identified
[ ] Users identified
[ ] Requirements documented
[ ] User stories created
[ ] Acceptance criteria defined
[ ] Scope defined
[ ] Out-of-scope items defined
[ ] Constraints documented
[ ] Assumptions documented
[ ] Risks identified
[ ] Feasibility checked
[ ] Technology selected
[ ] Architecture designed
[ ] Database designed
[ ] API designed
[ ] Security designed
[ ] UI/UX designed
[ ] Project structure defined
[ ] Development tasks created
[ ] Definition of Done defined
```

---

# Development Checklist

```text
[ ] Correct branch created
[ ] Task understood
[ ] Existing code inspected
[ ] Architecture followed
[ ] Input validation implemented
[ ] Error handling implemented
[ ] Authorization implemented
[ ] Logging added where appropriate
[ ] Tests added
[ ] Code formatted
[ ] Lint passes
[ ] Local tests pass
[ ] Commit created
```

---

# Code Review Checklist

```text
[ ] Requirement satisfied
[ ] Acceptance criteria satisfied
[ ] Code readable
[ ] Naming clear
[ ] Architecture respected
[ ] No unnecessary duplication
[ ] No obvious security issue
[ ] Error handling correct
[ ] Edge cases handled
[ ] Tests adequate
[ ] Performance acceptable
[ ] Documentation updated
```

---

# Pre-Production Checklist

```text
[ ] All tests pass
[ ] Security checks pass
[ ] Performance acceptable
[ ] Database migrations tested
[ ] Backup verified
[ ] Environment variables configured
[ ] Secrets configured
[ ] Monitoring configured
[ ] Logging configured
[ ] Alerts configured
[ ] Health checks working
[ ] Rollback plan ready
[ ] Staging validated
```

---

# Production Checklist

```text
[ ] Deployment approved
[ ] Backup confirmed
[ ] Deployment executed
[ ] Health checks pass
[ ] Logs normal
[ ] Error rate normal
[ ] Performance normal
[ ] Database healthy
[ ] Critical user flows tested
[ ] Rollback available
```

---

# Post-Production Checklist

```text
[ ] Monitor errors
[ ] Monitor performance
[ ] Review user feedback
[ ] Review analytics
[ ] Review incidents
[ ] Track technical debt
[ ] Update documentation
[ ] Create follow-up tasks
[ ] Plan next release
```

---

# 46. Project Documentation Structure

A mature project can use:

```text
docs/
│
├── 01-discovery/
│   ├── problem-statement.md
│   ├── business-requirements.md
│   ├── stakeholders.md
│   ├── personas.md
│   └── scope.md
│
├── 02-requirements/
│   ├── functional-requirements.md
│   ├── non-functional-requirements.md
│   ├── user-stories.md
│   └── use-cases.md
│
├── 03-planning/
│   ├── roadmap.md
│   ├── development-plan.md
│   ├── risks.md
│   └── definition-of-done.md
│
├── 04-architecture/
│   ├── system-design.md
│   ├── architecture.md
│   ├── database.md
│   ├── api.md
│   └── security.md
│
├── 05-design/
│   ├── ui-ux.md
│   ├── user-flows.md
│   └── wireframes.md
│
├── 06-development/
│   ├── coding-standards.md
│   ├── git-workflow.md
│   └── project-structure.md
│
├── 07-testing/
│   ├── test-strategy.md
│   ├── test-plan.md
│   ├── security-testing.md
│   └── performance-testing.md
│
├── 08-deployment/
│   ├── environments.md
│   ├── ci-cd.md
│   ├── deployment.md
│   └── rollback.md
│
├── 09-operations/
│   ├── monitoring.md
│   ├── logging.md
│   ├── incident-response.md
│   └── backup-recovery.md
│
├── 10-maintenance/
│   ├── technical-debt.md
│   ├── known-issues.md
│   └── roadmap.md
│
└── decisions/
    ├── ADR-001.md
    ├── ADR-002.md
    └── ADR-003.md
```

Not every small project needs every file.

Use the level of documentation appropriate to the project's complexity.

---

# 47. Senior Engineer Questions

Before development:

```text
What problem are we solving?

Who has the problem?

What is the actual requirement?

What is the MVP?

What are we NOT building?

What assumptions are we making?

What can go wrong?

What are the biggest technical risks?

Is the architecture appropriate?

Is there a simpler solution?

What happens when the database fails?

What happens when the API fails?

What happens when the network fails?

What happens when the user sends invalid data?

What happens when two users perform the same action simultaneously?

How will we secure the system?

How will we test it?

How will we deploy it?

How will we monitor it?

How will we roll it back?
```

---

# Questions During Development

```text
Am I solving the actual requirement?

Am I introducing unnecessary complexity?

Is this code in the correct layer?

Can this fail?

Have I handled the failure?

Is authorization enforced?

Is sensitive data protected?

Is this testable?

Is there duplication?

Will this scale?

Will another developer understand this?

What technical debt am I creating?
```

---

# Questions Before Release

```text
Does it work?

Does it work under failure?

Is it secure?

Is it tested?

Is it observable?

Can we deploy it safely?

Can we roll it back?

Is the database migration safe?

Are backups available?

Do we know what success means?
```

---

# Questions After Release

```text
Did users actually use it?

Did we solve the original problem?

Did performance degrade?

Did errors increase?

Did costs increase?

Did any security issues appear?

What did we learn?

What should we change?

What technical debt should we address?
```

---

# 48. Final Production Checklist

## Business

```text
[ ] Problem solved
[ ] Business objective achieved
[ ] MVP requirements completed
[ ] Stakeholder approval obtained
```

## Product

```text
[ ] User flows work
[ ] UX validated
[ ] Error states handled
[ ] Empty states handled
[ ] Accessibility considered
```

## Engineering

```text
[ ] Architecture implemented correctly
[ ] Database implemented correctly
[ ] APIs implemented correctly
[ ] Code quality acceptable
[ ] Technical debt tracked
```

## Security

```text
[ ] Authentication secure
[ ] Authorization secure
[ ] Input validation
[ ] Secrets protected
[ ] Sensitive data protected
[ ] Security testing completed
```

## Testing

```text
[ ] Unit tests
[ ] Integration tests
[ ] E2E tests where appropriate
[ ] Regression testing
[ ] Edge cases
[ ] Failure scenarios
```

## Performance

```text
[ ] API performance tested
[ ] Database queries checked
[ ] Resource usage checked
[ ] Load tested where required
```

## Operations

```text
[ ] Logging
[ ] Monitoring
[ ] Alerting
[ ] Health checks
[ ] Backups
[ ] Recovery plan
```

## Deployment

```text
[ ] CI/CD working
[ ] Staging validated
[ ] Production configuration verified
[ ] Migration tested
[ ] Rollback tested
```

## Documentation

```text
[ ] README
[ ] Architecture
[ ] API
[ ] Database
[ ] Security
[ ] Deployment
[ ] Troubleshooting
[ ] Changelog
```

---

# The Senior Engineer's Golden Workflow

When starting **any non-trivial project**, use this sequence:

```text
01. UNDERSTAND
    ↓
02. DEFINE THE PROBLEM
    ↓
03. GATHER REQUIREMENTS
    ↓
04. IDENTIFY USERS
    ↓
05. DEFINE SCOPE
    ↓
06. IDENTIFY CONSTRAINTS
    ↓
07. IDENTIFY RISKS
    ↓
08. VALIDATE FEASIBILITY
    ↓
09. SELECT TECHNOLOGY
    ↓
10. DESIGN ARCHITECTURE
    ↓
11. DESIGN DATABASE
    ↓
12. DESIGN APIs
    ↓
13. DESIGN SECURITY
    ↓
14. DESIGN UI/UX
    ↓
15. DEFINE PROJECT STRUCTURE
    ↓
16. BREAK INTO TASKS
    ↓
17. DEFINE ACCEPTANCE CRITERIA
    ↓
18. DEFINE DEFINITION OF DONE
    ↓
19. IMPLEMENT
    ↓
20. TEST
    ↓
21. REVIEW
    ↓
22. REFACTOR
    ↓
23. DOCUMENT
    ↓
24. CI/CD
    ↓
25. STAGING
    ↓
26. PRODUCTION
    ↓
27. MONITOR
    ↓
28. COLLECT FEEDBACK
    ↓
29. FIX / IMPROVE
    ↓
30. RETROSPECTIVE
    ↓
31. TECHNICAL DEBT
    ↓
32. NEXT ITERATION
```

---

# The Most Important Rule

Do not confuse **writing code** with **software engineering**.

```text
Coding
=
Writing implementation.

Software Engineering
=
Understanding the problem
+ requirements
+ architecture
+ design
+ security
+ implementation
+ testing
+ deployment
+ operations
+ maintenance
+ trade-offs.
```

The goal of a senior developer is not to write the most code.

The goal is to build the **simplest reliable system that solves the actual problem**, while making future change safe and affordable.

---

# Quick Reference

For a small project:

```text
Problem
→ Requirements
→ Scope
→ Design
→ Tasks
→ Code
→ Test
→ Review
→ Deploy
→ Monitor
```

For a medium/large production system:

```text
Problem
→ Business Requirements
→ Functional Requirements
→ Non-Functional Requirements
→ User Stories
→ Use Cases
→ Scope
→ Constraints
→ Risks
→ Feasibility
→ Technology Selection
→ System Architecture
→ Database Design
→ API Design
→ Security Design
→ UI/UX
→ Project Structure
→ Development Plan
→ Definition of Done
→ Implementation
→ Testing
→ Security Testing
→ Performance Testing
→ Code Review
→ Documentation
→ CI/CD
→ Staging
→ Production
→ Monitoring
→ Incident Response
→ Feedback
→ Technical Debt
→ Refactoring
→ Retrospective
→ Next Release
```

---

# Final Principle

> **Think first. Design second. Build third. Validate continuously. Operate responsibly. Improve continuously.**

A senior engineer is responsible not only for **whether the software works**, but also for:

```text
WHY it exists
WHAT it must do
HOW it should work
HOW it can fail
HOW it stays secure
HOW it is tested
HOW it is deployed
HOW it is monitored
HOW it is recovered
HOW it is maintained
HOW it evolves
```

That is the complete software engineering lifecycle.
