# Phase 09 — USE CASES

## 1. Purpose

This phase teaches how to capture detailed functional requirements using use cases, which describe interactions between actors (users or systems) and the system to achieve specific goals. Use cases provide a structured way to document functional requirements, including main flows, alternative flows, and error conditions.

## 2. What This Phase Is

This phase covers the fundamentals of use case modeling, including how to identify actors, define use cases, write main and alternative flows, document preconditions and postconditions, and use use cases to drive system design and testing.

## 3. Why This Phase Exists

While user stories capture what users want at a high level, use cases exist to:
- Provide detailed, step-by-step descriptions of system behavior
- Capture complex interactions and edge cases
- Serve as a foundation for system design, architecture, and testing
- Bridge the gap between high-level requirements and technical implementation
- Support traceability from requirements to design to tests
- Handle scenarios that are too complex for simple user stories

## 4. Where It Fits in the Software Development Lifecycle

Use cases come after:
- Problem Definition (Phase 2)
- Business Understanding (Phase 3)
- Stakeholder Analysis (Phase 4)
- User Research (Phase 5)
- User Personas (Phase 6)
- Requirements Overview (Phase 7)
- User Stories (Phase 8)

Use cases inform:
- Scope Definition (Phase 10)
- System Design (Phase 18)
- Architecture (Phase 19)
- Database Design (Phase 20)
- API Design (Phase 21)
- Security Design (Phase 22)
- UI/UX Design (Phase 23)
- Development Planning (Phase 21)
- Testing Strategy (Phase 29)

## 5. When This Phase Starts

This phase begins once user stories have been written and prioritized, and the team needs to detail complex interactions or prepare for system design.

## 6. What Must Be Known Before Starting

Before writing use cases, the team should understand:
- User personas and their goals (from Phases 5-6)
- High-level user stories (from Phase 8)
- Business objectives and value propositions
- The overall problem being solved
- Key system boundaries and scope

## 7. Inputs

Inputs to this phase include:
- User personas (from Phase 6)
- Prioritized user stories (from Phase 8)
- Business goals and objectives (from Phase 3)
- Problem statement (from Phase 2)
- Initial requirements overview (from Phase 7)
- Stakeholder analysis (from Phase 4)
- Any existing process documentation or workflows

## 8. Activities

Key activities in this phase:
- Identifying actors (primary, secondary, and system actors)
- Defining use cases based on user goals and stories
- Writing use case descriptions and preconditions/postconditions
- Detailing main success scenarios (basic flow)
- Identifying and documenting alternative flows
- Capturing error and exception flows
- Validating use cases with stakeholders
- Organizing use cases in a use case model or diagram
- Prioritizing use cases based on value and risk
- Tracing use cases to user stories and business objectives

## 9. Outputs / Deliverables

Outputs from this phase include:
- Use case diagram showing actors and use cases
- Detailed use case specifications (main flow, alternatives, etc.)
- Actor definitions and descriptions
- Use case prioritization and ranking
- Traceability matrix linking use cases to stories and objectives
- Use case package or organization structure
- Glossary of terms used in use cases
- Supplementary specifications (non-functional requirements)

## 10. Who Is Involved

Roles involved in this phase:
- Business Analysts (primary authors)
- Product Owner (for validation and prioritization)
- UX/UI Designers (for interaction flow input)
- Developers (for feasibility and technical constraint input)
- QA Engineers (for testability and test case input)
- System Architects (for architectural relevance)
- Subject Matter Experts (for domain knowledge)
- Stakeholders (for review and validation)

## 11. Step-by-Step Workflow

1. Review user stories and prioritize which ones need use case detail
2. Identify all actors (people, systems, hardware) that interact with the system
3. For each user story requiring detail, define a use case
4. Write use case name, brief description, and identify primary actor
5. Define preconditions (what must be true before use case starts)
6. Define postconditions (what will be true after use case completes)
7. Write the main success scenario (basic flow) step by step
8. Identify alternative flows (different paths, options, variations)
9. Identify error and exception flows (what can go wrong)
10. Define any special requirements (performance, security, etc.) for the use case
11. Review use case with stakeholders for accuracy and completeness
12. Update use case based on feedback
13. Organize use cases in a use case diagram or catalog
14. Trace use cases back to user stories and business objectives
15. Prioritize use cases for development

## 12. Real-World Example

For an online banking system:
- **Actor**: Bank Customer
- **Use Case**: Transfer Funds Between Accounts
- **Precondition**: Customer is logged into online banking
- **Postcondition**: Funds have been transferred and transaction recorded
- **Main Flow**:
  1. Customer selects "Transfer Funds"
  2. System displays list of customer's accounts
  3. Customer selects source account
  4. Customer selects destination account
  5. Customer enters transfer amount
  6. Customer enters optional memo/description
  7. Customer confirms transfer
  8. System validates sufficient funds
  9. System processes transfer
  10. System displays confirmation with transaction ID
  11. System updates account balances
- **Alternative Flows**:
  - Customer schedules transfer for future date
  - Customer transfers to external bank account (requires additional verification)
  - Customer uses saved transfer template
- **Error Flows**:
  - Insufficient funds: System displays error and prompts for different amount
  - Invalid account: System displays error and re-prompts for account selection
  - System timeout: System displays error and suggests retrying later

## 13. Junior Developer Perspective

Junior developers often:
- Confuse use cases with user stories or think they're redundant
- Write use cases that are too technical or focus on internal system behavior
- Forget to include alternative and error flows
- Make use cases too vague or lacking in specific detail
- Don't consider all relevant actors (especially system actors)
- Struggle with the right level of detail (too much or too little)
- Have difficulty writing clear, testable steps
- Don't connect use cases to user stories or business objectives

## 14. Senior Developer Perspective

Senior developers think about:
- How use cases will inform system architecture and design decisions
- What use cases reveal about system boundaries and interfaces
- How to structure use cases to support modular design
- What non-functional requirements emerge from use case analysis
- How use cases will be used to create test cases and test plans
- Whether use cases overlap or duplicate effort (need for consolidation)
- How to handle use cases that span multiple systems or services
- What use cases suggest about data flow and storage requirements
- How to use use cases for risk identification and mitigation
- How use cases evolve as understanding deepens during development

## 15. Common Mistakes

- Writing use cases as technical specifications rather than behavior descriptions
- Including UI design details in use case steps (should be technology-agnostic)
- Forgetting to define clear preconditions and postconditions
- Making use cases too large or complex (should be split if >10 steps)
- Not documenting alternative flows thoroughly enough
- Writing steps that combine multiple actions (violates atomic step principle)
- Using inconsistent terminology or actors across use cases
- Not validating use cases with actual users or subject matter experts
- Creating use cases that don't deliver clear user value
- Overlooking system-to-system interactions (focusing only on human actors)
- Writing use cases that are actually feature lists rather than behavioral descriptions

## 16. Security Considerations

Security considerations in use cases:
- Identifying authentication requirements at use case start
- Determining authorization checks needed during use case execution
- Considering what data is accessed, modified, or transmitted
- Identifying where input validation should occur
- Determining audit logging requirements for use case actions
- Considering session management aspects (timeout, etc.)
- Identifying encryption requirements for data in transit
- Considering privilege escalation or lateral movement risks
- Determining what security testing is needed for the use case
- Identifying any regulatory compliance requirements (GDPR, HIPAA, etc.)

## 17. Performance Considerations

Performance considerations in use cases:
- Identifying expected response time or throughput requirements
- Considering peak usage patterns and concurrent user loads
- Determining what caching or optimization might be needed
- Identifying resource-intensive operations that might need attention
- Considering data volume expectations and processing requirements
- Determining if asynchronous processing is appropriate
- Identifying any real-time or time-sensitive requirements
- Considering geographic distribution and latency requirements
- Determining what performance monitoring or metrics are needed
- Identifying any scalability concerns based on use case frequency

## 18. Scalability Considerations

Scalability considerations in use cases:
- Thinking about how use case volume will grow over time
- Considering whether use cases will need to work across multiple instances
- Determining if use cases create bottlenecks or single points of failure
- Considering data partitioning or sharding implications
- Thinking about how use cases will work in distributed systems
- Determining if use cases require eventual consistency considerations
- Considering API rate limiting or throttling needs
- Thinking about how use cases will handle bursts or spikes in usage
- Determining what horizontal vs. vertical scaling strategies apply
- Considering multi-tenancy implications if applicable

## 19. Quality Considerations

Quality considerations in use cases:
- Defining what constitutes successful completion of the use case
- Considering usability and accessibility requirements
- Determining what error handling and recovery procedures are needed
- Identifying monitoring and observability requirements
- Considering internationalization or localization needs
- Determining what validation or verification steps are required
- Considering backward compatibility requirements
- Defining what constitutes data quality or integrity for the use case
- Determining what quality gates or acceptance criteria apply

## 20. Definition of Done

A use case is considered done when:
- [ ] Use case name and description are clear and concise
- [ ] Primary and secondary actors are correctly identified
- [ ] Preconditions and postconditions are clearly defined
- [ ] Main success scenario is written as clear, numbered steps
- [ ] Alternative flows are identified and documented
- [ ] Error and exception flows are captured
- [ ] Use case has been reviewed and validated with stakeholders
- [ ] Use case is traceable to user stories and business objectives
- [ ] Non-functional requirements (performance, security, etc.) are considered
- [ ] Use case is atomic and focused on a single goal
- [ ] Steps are written at the appropriate level of detail (technology-agnostic)
- [ ] Use case delivers clear value to at least one actor
- [ ] Glossary terms are defined if needed

## 21. Completion Checklist

- [ ] All actors (human and system) have been identified
- [ ] Each use case has a clear, unambiguous name
- [ ] Each use case has a brief description of its purpose
- [ ] Preconditions state what must be true before use case begins
- [ ] Postconditions state what will be true after use case completes
- [ ] Main flow describes the happy path to achieving the use case goal
- [ ] Alternative flows cover different options, choices, or variations
- [ ] Error flows cover what can go wrong and how the system responds
- [ ] Steps are written in strong present tense with active voice
- [ ] Each step represents a single action or decision
- [ ] Steps avoid UI-specific details unless absolutely necessary
- [ ] Use case is independent or has clearly identified dependencies
- [ ] Use case has been prioritized based on business value and risk
- [ ] Traceability to user stories, requirements, and objectives is maintained
- [ ] Use case is understandable to both technical and non-technical stakeholders
- [ ] Any supplementary specifications (non-functional) are documented
- [ ] Use case has been validated for feasibility with development team

## 22. Related Phases

- Related to: Phase 5 (User Research), Phase 6 (User Personas), Phase 7 (Requirements), Phase 8 (User Stories)
- Informs: Phase 10 (Scope), Phase 18 (System Design), Phase 19 (Architecture), Phase 20 (Database Design), Phase 21 (API Design), Phase 22 (Security Design), Phase 23 (UI/UX Design), Phase 29 (Testing Strategy)
- Builds upon: All preceding discovery and analysis phases
- Enables: Design, development, testing, and validation phases