# 01 — USE CASE FUNDAMENTALS

## 1. What Is This?

Use cases are a requirements engineering technique that captures functional requirements by describing interactions between actors (users, systems, or hardware) and a system to achieve specific goals. They focus on what the system does from an external perspective, detailing sequences of actions and variations.

## 2. Why Does It Matter?

Use cases matter because they:
- Provide a structured, comprehensive way to capture functional requirements
- Focus on user goals and system behavior rather than technical implementation
- Capture both normal and exceptional system behavior
- Serve as a foundation for system design, architecture, and testing
- Support clear communication between stakeholders, analysts, developers, and testers
- Enable traceability from requirements through design to implementation and tests
- Help identify missing requirements through systematic analysis of interactions

## 3. What Problem Does It Solve?

Use cases address common requirements problems such as:
- Incomplete or missing requirements, especially edge cases and error conditions
- Misunderstandings between what users want and what developers build
- Requirements that are too vague or ambiguous to design or test from
- Overlooking system interactions and integration points
- Difficulty in validating requirements with users and stakeholders
- Poor traceability between high-level goals and detailed specifications
- Requirements documents that are difficult to navigate or maintain

## 4. When Should We Use It?

Use use cases when:
- Building systems with significant user interaction or complex workflows
- Requirements involve multiple user types or system-to-system interactions
- Detailed behavioral specification is needed for design and testing
- Regulatory or compliance requirements demand traceable specifications
- Systems have complex error handling or alternative processing paths
- Stakeholders benefit from visual or narrative requirement representations
- Replacing or supplementing user stories with more detailed specifications
- Developing systems where behavior is more important than data structure

## 5. When Should We NOT Use It?

Consider avoiding use cases when:
- Building simple systems with minimal user interaction
- Working in environments that strongly prefer user stories or other lightweight techniques
- Early-stage exploration where requirements are intentionally vague
- Systems that are primarily data-driven with simple CRUD operations
- Very small projects where overhead outweighs benefits
- Teams lack experience or training in use case modeling
- Requirements change extremely frequently, making detailed specs obsolete quickly
- Working with teams that reject formal requirements techniques

## 6. Core Concepts

### Actors
- **Primary Actor**: Has a goal requiring the system's assistance (initiates use case)
- **Secondary Actor**: Provides service to the system (system interacts with them)
- **System Actor**: Another system or component that interacts with the subject system
- **Actor Characteristics**: Role, not specific individual; can be human, hardware, or software

### Use Case Elements
- **Use Case**: Represents a goal that an actor wants to achieve
- **Subject System**: The system being designed or discussed
- **Stakeholder**: Anyone with interest in the system's behavior
- **Precondition**: What must be true before the use case can start
- **Postcondition**: What will be true after the use case completes successfully
- **Main Success Scenario (Basic Flow)**: Step-by-step interaction when everything goes right
- **Alternative Flows**: Variations from the main flow (options, choices, different paths)
- **Error Flows**: What happens when something goes wrong (exceptions, failures)
- **Trigger**: Event that initiates the use case (often from primary actor)
- **Guarantees**: What the use case promises to the actors involved

### Relationships
- **Include**: Factoring out common behavior used by multiple use cases
- **Extend**: Adding optional behavior to a base use case under certain conditions
- **Generalization**: Specializing a use case (inheritance-like relationship)
- **Extends vs. Includes**: Include is always mandatory; Extend is optional and conditional

### Levels of Use Cases
- **Summary-Level**: High-level, user-goal oriented (often equivalent to epics)
- **User-Goal Level**: Typical use case representing a discrete user task
- **Subfunction Level**: Low-level, often too detailed for requirements (better for design)

## 7. Step-by-Step Process

1. **Identify Actors**: List all entities that interact with the system
2. **Identify Use Cases**: For each actor goal, define a use case
3. **Define Scope**: Clearly state what is and isn't included
4. **Write Use Case Brief**: Short description of purpose and value
5. **Identify Primary Actor**: Who initiates this use case and what is their goal?
6. **Define Preconditions**: Conditions that must be true before starting
7. **Define Postconditions**: Conditions that will be true after successful completion
8. **Write Main Success Scenario**: Numbered steps of the happy path
9. **Identify Alternative Flows**: Different paths, options, or variations
10. **Identify Error Flows**: What can go wrong and how system responds
11. **Define Special Requirements**: Non-functional needs specific to this use case
12. **Review with Stakeholders**: Validate accuracy, completeness, and value
13. **Refine Based on Feedback**: Update as understanding evolves
14. **Organize and Prioritize**: Group related use cases and prioritize for implementation
15. **Trace to Requirements**: Link use cases to user stories, business objectives, etc.

## 8. Inputs

Inputs to creating use cases include:
- User personas and their goals (from Phases 5-6)
- Prioritized user stories (from Phase 8)
- Business objectives and value propositions
- Current state documentation or process descriptions
- Stakeholder interviews and workshops
- Problem statement and opportunity analysis
- Regulatory and compliance requirements
- Technology constraints and opportunities
- Existing systems or legacy interfaces to consider
- Non-functional requirements and quality attributes
- User journey maps or experience maps
- Competitive analysis and market research
- Feedback from customer support or sales teams

## 9. Outputs / Deliverables

Outputs from use case creation include:
- Use case diagram showing actor-use case relationships
- Fully dressed use case templates with all sections completed
- Actor catalog with descriptions and responsibilities
- Use case catalog or repository
- Traceability matrices (use cases to stories, objectives, etc.)
- Glossary of domain-specific terms used in use cases
- Supplementary specifications (non-functional requirements)
- Use case packages or organizational structure
- Prioritized use case backlog or roadmap
- Validation meeting minutes and stakeholder sign-off
- Test case derivation guidelines or matrices

## 10. Real-World Example

**Use Case Name**: Place Order  
**Primary Actor**: Online Customer  
**Secondary Actors**: Payment System, Inventory System, Email Service  
**Description**: A customer purchases products from the online store.  

**Precondition**: Customer has browsed catalog and added items to shopping cart  
**Postcondition**: Order is recorded, payment processed, inventory reduced, confirmation sent  

**Main Success Scenario**:
1. Customer proceeds to checkout
2. System displays shopping cart contents and total
3. Customer enters shipping address
4. Customer selects shipping method
5. System calculates taxes and shipping costs
6. Customer enters payment information
7. System validates payment with payment gateway
8. System checks inventory availability for all items
9. System creates order record with pending status
10. System authorizes payment with payment gateway
11. System reserves inventory items
12. System captures payment from payment gateway
13. System updates inventory levels
14. System sends order confirmation email
15. System displays order confirmation page with order number

**Alternative Flows**:
- 6a. Customer uses saved payment method instead of entering new details
- 6b. Customer applies discount coupon or promotional code
- 6c. Customer chooses to save shipping address for future use
- 9a. Item out of stock: System suggests alternatives or allows backorder
- 9b. Inventory discrepancy: System alerts customer and allows partial order

**Error Flows**:
- 7a. Payment declined: System displays error and prompts for different payment
- 7b. Payment gateway timeout: System displays error and suggests retrying later
- 10a. Insufficient inventory: System notifies customer and removes item from cart
- 14a. Email service failure: System logs error but order remains valid

**Special Requirements**:
- Performance: Complete checkout in under 5 seconds
- Security: PCI-DSS compliance for payment processing
- Availability: 99.9% uptime for checkout process
- Auditing: All payment and inventory changes must be logged

## 11. Technical Example

**Use Case Name**: Authenticate User via API  
**Primary Actor**: API Client (Mobile App, Web App, or Partner System)  
**Secondary Actor**: User Database, Authentication Service, Audit Log  
**Description**: An external system authenticates a user to gain access to protected resources.  

**Precondition**: API client has valid API credentials and endpoint URL  
**Postcondition**: Valid authentication token issued or clear authentication failure  

**Main Success Scenario**:
1. API client sends POST request to /auth/login with username and password
2. System validates request format and required fields
3. System checks username exists in user database
4. System verifies password hash matches stored hash
5. System generates JWT token with user ID, roles, and expiration
6. System records successful authentication in audit log
7. System returns HTTP 200 with token in response body
8. API client receives and stores token for subsequent requests

**Alternative Flows**:
- 3a. Username not found: System returns HTTP 401 (invalid credentials)
- 4a. Password incorrect: System returns HTTP 401 (invalid credentials)
- 5a. Token generation fails: System returns HTTP 500 with error details
- 6a. Audit log unavailable: System continues but logs warning internally

**Error Flows**:
- 1a. Malformed JSON: System returns HTTP 400 with validation errors
- 1a. Missing credentials: System returns HTTP 400 with required fields
- 1a. Expired API credentials: System returns HTTP 403 (forbidden)
- 5a. Token signing key unavailable: System returns HTTP 503 (service unavailable)

**Special Requirements**:
- Performance: Respond in under 200ms under normal load
- Security: Use bcrypt or Argon2 for password hashing, TLS 1.2+ for transport
- Rate Limiting: Maximum 10 attempts per username per 15 minutes
- Auditing: Log all attempts (success and failure) with timestamps and IP addresses
- Availability: Designed for 99.95% uptime with automatic failover

## 12. Good Approach

- Focus on actor goals, not system functions or features
- Write from the actor's perspective ("the system does X" not "the user clicks Y")
- Keep use cases at the right level of detail (user-goal level, not subfunction)
- Use strong present tense and active voice in step descriptions
- Make each step represent a single, atomic action or decision
- Avoid UI-specific details unless they're essential to the behavior
- Clearly distinguish between main flow, alternatives, and error flows
- Ensure preconditions and postconditions are meaningful and testable
- Write steps that are unambiguous and leave no room for interpretation
- Include both what the system does and what the actor does in each step
- Use clear, consistent terminology throughout the use case
- Validate that the use case delivers tangible value to the primary actor
- Consider how the use case might be split if it becomes too complex
- Think about performance, security, and other NFRs early in the process
- Ensure use cases are independent or have clearly documented dependencies
- Write use cases that are technologically neutral where possible
- Consider the use case's reusability across different contexts or systems

## 13. Bad Approach

- Writing use cases as technical specifications (button clicks, database queries)
- Including design decisions or technology choices in use case steps
- Making use cases too vague ("system processes the order")
- Writing steps that combine multiple actions (violates atomic step principle)
- Forgetting to define clear preconditions and postconditions
- Writing use cases that are actually feature lists rather than behavior descriptions
- Including UI design specifics unless absolutely required for behavior
- Making use cases too large (>15 steps) without considering splitting
- Using passive voice or weak language that obscures responsibility
- Writing steps that are implementation-specific rather than behavior-focused
- Forgetting to consider alternative paths or error conditions
- Creating use cases that don't have a clear primary actor or goal
- Writing use cases that are duplicative or overlap significantly with others
- Including non-functional requirements in the main flow steps
- Writing use cases that are impossible to test or validate objectively
- Using inconsistent terminology or actor names across related use cases
- Forgetting to consider the system's boundaries and interfaces

## 14. Common Mistakes

- Confusing use cases with user stories or thinking they serve the same purpose
- Writing use cases from the system's perspective instead of the actor's
- Omitting secondary actors that are essential to the use case success
- Making preconditions too weak or postconditions too vague
- Writing main flow steps that are actually alternative or error handling
- Forgetting to number steps or using inconsistent numbering
- Using future tense ("will do") or past tense ("did") instead of present
- Writing steps that containconditional logic without specifying the condition
- Not considering timeouts, retries, or asynchronous behavior
- Overlooking data validation and sanitization requirements
- Missing system initialization or cleanup steps
- Forgetting to consider usability or accessibility aspects
- Not thinking about how the use case behaves under partial failure
- Writing use cases that are actually user stories in disguise
- Not validating use cases with actual users or domain experts
- Creating use cases that are too granular (better suited for design)
- Forgetting to consider internationalization or localization needs
- Not thinking about how use cases will be tested or validated
- Overlooking the need for a glossary of domain-specific terms
- Forgetting to consider versioning or evolution of use cases over time

## 15. Security Considerations

When writing use cases, consider:
- **Authentication**: Who needs to prove their identity to use this functionality?
- **Authorization**: What permissions or roles are required at different steps?
- **Data Protection**: What sensitive data is accessed, modified, or transmitted?
- **Input Validation**: Where and how should inputs be validated to prevent injection?
- **Authentication Bypass**: What would happen if authentication is skipped?
- **Privilege Escalation**: Could this use case be used to gain higher privileges?
- **Information Leakage**: Could error messages reveal sensitive information?
- **Session Management**: How are sessions created, maintained, and invalidated?
- **Audit Trail**: What security-relevant events should be logged?
- **Encryption Requirements**: What data needs encryption in transit or at rest?
- **Secure Defaults**: Are secure configurations used unless explicitly changed?
- **Third-Party Dependencies**: Are external services or libraries used securely?
- **Security Testing**: What penetration testing or vulnerability scanning is needed?
- **Compliance Requirements**: What regulatory standards (PCI-DSS, HIPAA, GDPR) apply?
- **Attack Surface**: What potential attack vectors does this use case expose?
- **Defensive Coding**: What input sanitization or output encoding is needed?

## 16. Performance Considerations

When writing use cases, consider:
- **Response Time**: How quickly should the system respond to user actions?
- **Throughput**: How many executions per second/minute/hour are expected?
- **Resource Usage**: What are acceptable CPU, memory, disk, or network consumption levels?
- **Concurrent Users**: How many simultaneous executions should be supported?
- **Data Volumes**: What amounts of data will be processed or transferred?
- **Peak Loads**: How should the system behave during usage spikes or bursts?
- **Latency Sensitivity**: Is timing critical for any steps in the use case?
- **Scalability Needs**: Will performance requirements change as usage grows?
- **Caching Opportunities**: Where could caching improve performance without breaking behavior?
- **Database Optimization**: What queries or access patterns need optimization?
- **Asynchronous Processing**: Which steps could be decoupled for better responsiveness?
- **Blocking Operations**: What operations might cause threads or processes to block?
- **Network Calls**: How many external service calls are made and what are their timeouts?
- **Content Delivery**: Are static assets or media files involved that could benefit from CDNs?
- **Monitoring Needs**: What performance metrics should be collected and alerted on?
- **Degradation Behavior**: How should the system behave when operating near capacity limits?

## 17. Scalability Considerations

When writing use cases, consider:
- **Horizontal Scaling**: Can multiple instances handle the load through load balancing?
- **State Management**: How is user or session state maintained across instances?
- **Data Distribution**: How will data be partitioned as volume grows?
- **Database Scaling**: Will current database choice support anticipated growth?
- **Caching Strategy**: What caching approach (local, distributed, hierarchical) is appropriate?
- **Message Queuing**: Should asynchronous processing use queues or similar mechanisms?
- **Microservices Boundaries**: Does this use case suggest service boundaries?
- **Event-Driven Architecture**: Could parts be better handled asynchronously via events?
- **API Rate Limiting**: Will external service calls need throttling or quota management?
- **Geographic Distribution**: Will users be globally distributed requiring edge computing?
- **Multi-tenancy**: If applicable, how will resource isolation and sharing work?
- **Eventual Consistency**: Can the use case tolerate temporary inconsistencies?
- **Failure Domains**: How do failure scenarios affect scalability and availability?
- **Resource Contention**: What resources might become bottlenecks under scale?
- **Elastic Scaling**: Can the system automatically add/remove capacity based on demand?
- **Performance Testing**: What load, stress, and soak testing is needed?
- **Capacity Planning**: What are the projected limits and when will upgrades be needed?

## 18. Maintainability Considerations

When writing use cases, consider:
- **Clarity and Simplicity**: Is the use case easy to understand and modify?
- **Consistency**: Does terminology and style match other use cases?
- **Abstraction Level**: Is it at the right level (not too detailed, not too vague)?
- **Dependency Management**: Are dependencies clear and managed appropriately?
- **Duplication Reduction**: Is common behavior factored out using include/extend?
- **Testability**: Can the use case be easily validated through manual or automated tests?
- **Observability**: Can execution be monitored and debugged effectively?
- **Extensibility**: Will it be easy to add variations or extend functionality later?
- **Modularity**: Does it support modular design and implementation approaches?
- **Standards Compliance**: Does it follow organizational or industry use case standards?
- **Documentation Needs**: What additional documentation will be needed for implementation?
- **Knowledge Transfer**: Will new team members be able to understand it easily?
- **Technical Debt**: Does implementing it as-written risk creating technical debt?
- **Refactoring Friendly**: Is the behavior structured to support future refactoring?
- **Change Impact**: How likely is it to need changes as requirements evolve?
- **Reusability**: Can parts be reused in other contexts or systems?
- **Validation Approach**: How will correctness be validated over time?

## 19. Junior Developer Approach

Junior developers typically:
- Focus on system internals rather than actor behavior
- Write use cases that read like technical specifications or design documents
- Forget to include alternative and error flows entirely
- Make use cases too vague or lacking in concrete detail
- Confuse actors with specific job titles or individuals rather than roles
- Struggle with the right granularity (too fine or too coarse)
- Write steps that combine multiple actions or decisions
- Include UI-specific details unless absolutely necessary for behavior
- Have difficulty writing clear preconditions and postconditions
- Overlook secondary actors that are essential to use case success
- Write use cases that are actually feature lists rather than behavior descriptions
- Need examples and practice to understand what makes a good use case
- Benefit from templates and checklists when getting started
- Often write use cases that are too large and need splitting
- May not consider non-functional requirements in use case analysis
- Struggle to connect use cases to user stories or business objectives

## 20. Senior Developer Approach

Senior developers think about:
- How use cases will inform functional decomposition and module design
- What architectural patterns or styles are suggested by use case analysis
- How to structure use cases to support loose coupling and high cohesion
- What use cases reveal about system boundaries, interfaces, and contracts
- How use cases will be used to derive test cases (unit, integration, system)
- Whether use cases suggest synchronous vs. asynchronous processing needs
- What data consistency models are implied by different use cases
- How to use use cases for performance modeling and capacity planning
- How use cases inform security design (authentication, authorization, auditing)
- Whether use cases suggest the need for caching, queuing, or buffering
- How to split complex use cases while preserving behavioral integrity
- What use cases suggest about technology choices (build vs. buy, tech stack)
- How to use use cases for risk identification and mitigation planning
- How use cases evolve during development as understanding deepens
- Whether to create exploratory use cases first, then refine to detailed ones
- How to balance detail level with flexibility in implementation
- What makes a use case "good enough" to move forward with design

## 21. Senior Engineer Questions

Senior engineers ask:
- "What is the smallest version of this use case that delivers real value?"
- "How would we know if we built the wrong thing even if the use case passes?"
- "What assumptions are we making about actor behavior or system context?"
- "How expensive or difficult will it be to verify each part of the use case?"
- "Could we achieve the same validation with fewer, smarter use cases?"
- "What would make us realize these use cases are inadequate after release?"
- "How do these use cases affect our ability to change or refactor later?"
- "Are we testing the right things, or just what's easy to test?"
- "What non-functional aspects should be elevated to explicit use case considerations?"
- "How do these use cases interact with related use cases (include/extend/generalization)?"
- "What measurement approaches would validate these use cases in production?"
- "Are we writing use cases to pass reviews, or to ensure real user and system value?"
- "What would happen if we reversed the roles of primary and secondary actors?"
- "How does this use case behave when part of the system is degraded or unavailable?"
- "What would make us split this use case, and how would we do it?"
- "How do we handle use cases that span multiple systems or organizations?"
- "What is the cost of coordination between use cases vs. building integrated features?"
- "Are we capturing the real goal, or just a intermediate step toward it?"
- "How do seasonal, burst, or peak usage patterns affect this use case?"

## 22. Practical Exercise

**Exercise**: Write a use case for the following scenario:

**Scenario**: A library patron wants to borrow a book from the public library using the self-checkout kiosk.

For this use case:
1. Identify the primary and secondary actors
2. Write a clear use case name and brief description
3. Define meaningful preconditions and postconditions
4. Write the main success scenario as numbered steps (5-8 steps)
5. Identify 2-3 alternative flows (different options or variations)
6. Identify 2-3 error flows (what can go wrong and how the system responds)
7. Consider any special requirements (performance, security, etc.)
8. Ensure steps are written from the actor's perspective, not system internals
9. Avoid UI-specific details unless essential to the behavior
10. Use strong present tense and active voice throughout

## 23. Definition of Done

A use case is considered complete when:
- [ ] Use case name clearly communicates the actor's goal
- [ ] Primary actor is correctly identified and has a clear goal
- [ ] Secondary actors are identified if they participate in the use case
- [ ] Brief description explains the use case's purpose and value
- [ ] Preconditions are specific, meaningful, and testable
- [ ] Postconditions describe the successful end state
- [ ] Main success scenario is written as clear, numbered steps
- [ ] Each step represents a single action or decision from actor's perspective
- [ ] Steps avoid implementation details unless absolutely necessary for behavior
- [ ] Alternative flows cover meaningful variations or options
- [ ] Error flows cover reasonably likely failure modes
- [ ] Steps use strong present tense and active voice consistently
- [ ] Terminology is consistent with other use cases and domain glossary
- [ ] Use case has been reviewed and validated with stakeholders
- [ ] Non-functional requirements (performance, security, etc.) are considered
- [ ] Use case delivers clear value to the primary actor
- [ ] Use case is independent or has identified dependencies
- [ ] Traceability to user stories, requirements, or business objectives exists
- [ ] Glossary terms are defined if domain-specific language is used
- [ ] Use case is appropriately sized (typically 3-10 steps for main flow)

## 24. Checklist

- [ ] Does the use case focus on what the actor wants to accomplish?
- [ ] Is the primary actor correctly identified as the initiator with a goal?
- [ ] Are secondary actors correctly identified as helpers or services?
- [ ] Does the use case name use strong verb-noun phrasing (e.g., "Place Order")?
- [ ] Is the brief description concise yet informative?
- [ ] Are preconditions specific conditions that must be true before starting?
- [ ] Are postconditions specific conditions that will be true after completion?
- [ ] Does the main flow represent the happiest path to the goal?
- [ ] Are steps written in strong present tense with active voice?
- [ ] Does each step represent a single action or decision?
- [ ] Have UI-specific details been avoided unless essential to behavior?
- [ ] Have all steps been reviewed for clarity and unambiguity?
- [ ] Are alternative flows meaningful variations, not just error handling?
- [ ] Are error flows realistic failures with appropriate system responses?
- [ ] Have we considered performance expectations or requirements?
- [ ] Have we considered security, authentication, or authorization needs?
- [ ] Have we considered any special regulatory or compliance requirements?
- [ ] Is the use case appropriately sized for a user-goal level use case?
- [ ] Have we checked for consistency with other use cases in terminology?
- [ ] Have we validated the use case with stakeholders or subject matter experts?
- [ ] Is traceability maintained to user stories, requirements, or objectives?
- [ ] Have we considered how this use case would be tested?
- [ ] Are steps free of implementation details like database queries or API calls?
- [ ] Does the use case avoid describing internal system architecture or design?
- [ ] Would someone unfamiliar with the system understand the use case?
- [ ] Is the use case technologically neutral where possible?

## 25. Related Topics

- Related to: 02-ACTOR-DEFINITION.md (actor specifics), 03-MAIN-FLOW.md (basic flow), 04-ALTERNATIVE-FLOW.md (alternatives), 05-FAILURE-FLOW.md (error handling)
- Builds upon: Agile requirements techniques, user-centered design, UML use case modeling
- Enables: System design, architecture, test case creation, interface specification
- Related to: User stories, scenario modeling, event-driven design, requirements tracing, functional decomposition, specification by example, Gherkin, Cucumber, Behavioral-Driven Development (BDD)