# Phase 08 — USER STORIES

## 1. Purpose

This phase teaches how to capture functional requirements as user stories, which are concise descriptions of features told from the perspective of the end user. User stories help bridge the gap between business needs and technical implementation by focusing on who wants what and why.

## 2. What This Phase Is

This phase covers the fundamentals of user stories, including their format (As a [role], I want [goal] so that [benefit]), how to write effective acceptance criteria, techniques for splitting large stories, and how user stories fit into agile development processes.

## 3. Why This Phase Exists

Traditional requirements documents often fail to capture user context and value. User stories exist to:
- Keep focus on user value rather than technical details
- Enable conversations between developers, product owners, and users
- Provide a flexible format that can evolve with understanding
- Support incremental delivery and prioritization
- Create a shared understanding of what needs to be built

## 4. Where It Fits in the Software Development Lifecycle

User stories come after:
- Problem Definition (Phase 2)
- Business Understanding (Phase 3)
- Stakeholder Analysis (Phase 4)
- User Research (Phase 5)
- User Personas (Phase 6)
- Requirements Overview (Phase 7)

User stories inform:
- Use Cases (Phase 9)
- Scope Definition (Phase 10)
- Prioritization (Phase 11)
- Development Planning (Phase 21)
- Testing Strategy (Phase 29)

## 5. When This Phase Starts

This phase begins once user research has been synthesized into personas and the team has a clear understanding of who the users are and what problems they face.

## 6. What Must Be Known Before Starting

Before writing user stories, the team should understand:
- User personas and their goals
- Business objectives and value propositions
- High-level functional and non-functional requirements
- Constraints and assumptions
- The overall problem being solved

## 7. Inputs

Inputs to this phase include:
- User personas (from Phase 6)
- User research findings (from Phase 5)
- Business goals and objectives (from Phase 3)
- Problem statement (from Phase 2)
- Initial requirements overview (from Phase 7)

## 8. Activities

Key activities in this phase:
- Writing user stories using the standard format
- Defining clear acceptance criteria for each story
- Reviewing and refining stories with stakeholders
- Splitting large stories into smaller, manageable pieces
- Prioritizing stories based on value and risk
- Estimating effort for planning purposes
- Organizing stories into a product backlog

## 9. Outputs / Deliverables

Outputs from this phase include:
- A product backlog of user stories
- Acceptance criteria for each story
- Story estimates (if using estimation techniques)
- Story maps or release plans
- Definitions of ready and done for stories
- Updated requirements traceability matrix

## 10. Who Is Involved

Roles involved in this phase:
- Product Owner (primary author and maintainer)
- Business Analysts (facilitators)
- UX/UI Designers (for user perspective input)
- Developers (for feasibility feedback)
- QA Engineers (for testability input)
- UX Researchers (for user validation)
- Stakeholders (for review and feedback)

## 11. Step-by-Step Workflow

1. Review user personas and research findings
2. Brainstorm potential user stories from persona goals
3. Write stories using the "As a [role], I want [goal] so that [benefit]" format
4. Define acceptance criteria using Given/When/Then format
5. Review stories with the development team for feasibility
6. Split stories that are too large (>1 sprint)
7. Estimate story size using story points or ideal days
8. Prioritize stories based on business value and dependencies
9. Refine stories based on feedback
10. Add stories to the product backlog
11. Update requirements traceability

## 12. Real-World Example

For an e-commerce food delivery app:
- As a hungry customer, I want to see restaurant menus so that I can decide what to order
- As a delivery driver, I want to see the optimal route so that I can make deliveries efficiently
- As a restaurant owner, I want to receive order notifications so that I can prepare food promptly

## 13. Junior Developer Perspective

Junior developers often:
- Focus only on the "I want" part and forget the "so that" (value) component
- Write stories that are too technical or implementation-focused
- Skip writing acceptance criteria entirely
- Create stories that are too large to complete in a sprint
- Don't consider edge cases or error conditions

## 14. Senior Developer Perspective

Senior developers think about:
- How the story will be tested and what test cases are needed
- What dependencies exist with other stories or systems
- What performance or security considerations apply
- How the story might need to evolve based on feedback
- What technical debt might be introduced and how to mitigate it
- Whether the story reveals gaps in the architecture or data model

## 15. Common Mistakes

- Writing stories as technical tasks rather than user-facing features
- Making stories too vague or ambiguous
- Forgetting to include acceptance criteria
- Not involving actual users in story validation
- Creating stories that depend on unknown factors
- Writing stories that cannot be independently tested or deployed
- Not updating stories as understanding evolves

## 16. Risks

Risks associated with poor user stories:
- Building features that don't solve real user problems
- Misalignment between what users want and what gets built
- Scope creep due to unclear boundaries
- Difficulty in estimating and planning
- Increased rework due to misunderstood requirements
- Poor test coverage due to unclear acceptance criteria

## 17. Security Considerations

Security considerations in user stories:
- Identifying when authentication or authorization is needed
- Considering what data the user will access or modify
- Thinking about input validation requirements
- Identifying privacy considerations for personal data
- Considering audit logging needs for sensitive actions
- Identifying potential abuse cases or misuse scenarios

## 18. Performance Considerations

Performance considerations in user stories:
- Identifying expected response times or throughput needs
- Considering concurrent user loads
- Thinking about data volume expectations
- Identifying peak usage patterns
- Considering offline or degraded mode requirements
- Thinking about caching or optimization needs

## 19. Scalability Considerations

Scalability considerations in user stories:
- Thinking about how features will handle growth
- Considering geographic distribution needs
- Identifying multi-tenancy requirements if applicable
- Thinking about data partitioning or sharding needs
- Considering API rate limits or throttling
- Identifying when asynchronous processing might be needed

## 20. Quality Considerations

Quality considerations in user stories:
- Defining what "done" means for each story
- Considering usability and accessibility requirements
- Thinking about error handling and recovery
- Identifying monitoring and observability needs
- Considering internationalization or localization needs
- Thinking about backward compatibility requirements

## 21. Definition of Done

A user story is considered done when:
- [ ] The story is written in proper format
- [ ] Acceptance criteria are clear and testable
- [ ] The story has been reviewed by the team
- [ ] Any dependencies have been identified
- [ ] The story has been estimated (if using estimation)
- [ ] The story is small enough to complete in one sprint
- [ ] Acceptance criteria can be used to create test cases
- [ ] The story provides clear user value
- [ ] Non-functional requirements (performance, security) are considered

## 22. Completion Checklist

- [ ] All user personas have associated stories
- [ ] Stories cover all major user goals
- [ ] Acceptance criteria are written for each story
- [ ] Stories are independent and negotiable
- [ ] Stories provide clear business value
- [ ] Stories are estimable and small enough to plan
- [ ] Stories have been reviewed with stakeholders
- [ ] Duplicate or overlapping stories have been merged
- [ ] Stories are prioritized in the backlog
- [ ] Traceability to business objectives is maintained

## 23. Related Phases

- Related to: Phase 5 (User Research), Phase 6 (User Personas), Phase 7 (Requirements), Phase 9 (Use Cases)
- Informs: Phase 10 (Scope), Phase 11 (Prioritization), Phase 21 (Development Planning), Phase 29 (Testing Strategy)
- Builds upon: All user-centered phases (5-7)
- Enables: Development, testing, and delivery phases