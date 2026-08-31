# 04 — STORY SPLITTING

## 1. What Is This?

Story splitting is the technique of breaking down large user stories (often called epics) into smaller, more manageable pieces that can be completed within a single sprint or iteration. This process ensures that stories are small enough to be estimated, developed, tested, and delivered effectively while still delivering user value.

## 2. Why Does It Matter?

Story splitting matters because it:
- Enables incremental delivery and faster feedback
- Makes estimation more accurate and reliable
- Reduces risk by delivering value early and often
- Improves flow and predictability in the development process
- Allows for better prioritization and flexibility
- Helps teams maintain a sustainable pace
- Facilitates easier testing and quality assurance
- Supports continuous integration and deployment practices
- Enables more accurate forecasting and planning

## 3. What Problem Does It Solve?

Large stories (epics) cause problems such as:
- Difficulty in estimation leading to planning inaccuracies
- Long feedback cycles delaying learning and adaptation
- Increased risk of failure due to complexity and uncertainty
- Bottlenecks in development and testing phases
- Difficulty in tracking progress and measuring velocity
- Challenges in adapting to changing requirements
- Poor visibility into work-in-progress
- Tendency to accumulate technical debt due to rushed completion
- Misalignment between business expectations and delivery reality

## 4. When Should We Use It?

Use story splitting when:
- A story is too large to fit within a single sprint
- Estimating the story feels uncertain or risky
- The story encompasses multiple distinct user goals
- The story has complex acceptance criteria
- Dependencies make the story difficult to isolate
- You want to deliver value earlier rather than later
- The story involves significant learning or uncertainty
- You need to split work for parallel development
- Preparing for release planning or roadmapping

## 5. When Should We NOT Use It?

Consider avoiding story splitting when:
- The story is already small enough to complete in a sprint
- Splitting would diminish the user value or coherence
- The effort to split outweighs the benefits (very small stories)
- Working on spike or research stories where the goal is learning
- The story represents a non-functional requirement or technical constraint
- The story is truly atomic and cannot be meaningfully divided
- Early prototyping where exploration is more valuable than delivery
- Stories that are placeholders for future detailed work

## 6. Core Concepts

### INVEST Criteria Reminder
Good stories should be Independent, Negotiable, Valuable, Estimable, Small, and Testable. Story splitting helps achieve these qualities.

### Splitting vs. Slicing
- **Splitting**: Breaking a story into multiple stories that collectively deliver the same functionality
- **Slicing**: Creating a thin vertical slice through all layers of an application to deliver end-to-end functionality

### Story Mapping Context
Story splitting often occurs within the context of user story mapping, where epics are broken down along user journey steps.

### Splitting Dimensions
Stories can be split along various dimensions:
- User roles or personas
- Steps in a user journey
- Business rule variations
- Data boundaries
- Operational boundaries (CRUD operations)
- Complexity levels (simple → advanced)
- Input methods or channels
- Platforms or devices
- Non-functional requirements (performance, security, etc.)
- Temporal boundaries (time-based workflows)

## 7. Step-by-Step Process

1. **Identify oversized stories**: Look for stories that exceed sprint capacity
2. **Understand the core value**: What is the essential user benefit?
3. **Choose splitting dimension**: Select an appropriate axis for splitting
4. **Create child stories**: Break the epic into smaller, valuable pieces
5. **Verify INVEST qualities**: Ensure each child story meets good story criteria
6. **Check for dependencies**: Identify and manage relationships between split stories
7. **Estimate child stories**: Assign effort estimates for planning
8. **Prioritize split stories**: Order them based on value and risk
9. **Update backlog**: Replace the epic with its split stories
10. **Track progress**: Monitor completion of split stories toward epic goals

## 8. Inputs

Inputs to story splitting include:
- Large user stories or epics from the backlog
- Sprint capacity and velocity metrics
- Definition of Done and team capacity understanding
- User journey maps or process flows
- Business rules and requirements documents
- User feedback and pain points
- Technical architecture and constraints
- Dependencies on other stories or systems
- Regulatory or compliance requirements
- Performance, security, or usability requirements
- Release planning goals and timelines
- Stakeholder priorities and expectations

## 9. Outputs / Deliverables

Outputs from story splitting include:
- Multiple smaller user stories replacing the original epic
- Clear acceptance criteria for each split story
- Updated story estimates and priorities
- Identification of dependencies between split stories
- Improved backlog visibility and transparency
- Enhanced ability to track progress toward epic completion
- Better alignment between development capacity and commitments
- Increased opportunities for early feedback and validation
- Documentation of splitting rationale for future reference

## 10. Real-World Example

**Epic**: As a customer, I want to manage my online shopping account so that I can control my personal information, payment methods, and order history.

**Split Stories**:
1. As a customer, I want to update my profile information (name, email, phone) so that my account details stay current.
2. As a customer, I want to add a new payment method so that I have multiple options for purchases.
3. As a customer, I want to set a default payment method so that I don't need to select it each time.
4. As a customer, I want to view my order history so that I can track past purchases.
5. As a customer, I want to save multiple shipping addresses so that I can ship to different locations.
6. As a customer, I want to delete a payment method so that I can remove outdated or compromised cards.
7. As a customer, I want to change my password so that I can maintain account security.
8. As a customer, I want to subscribe/unsubscribe from promotional emails so that I control my communications.

## 11. Technical Example

**Epic**: As a developer, I want to integrate with the payment gateway so that I can process transactions securely.

**Split Stories**:
1. As a developer, I want to establish a secure connection to the payment gateway API so that I can begin integration.
2. As a developer, I want to implement payment authorization so that I can verify funds availability.
3. As a developer, I want to implement payment capture so that I can collect authorized funds.
4. As a developer, I want to handle payment refunds so that I can return funds to customers.
5. As a developer, I want to implement webhook handling for payment events so that I can react to asynchronous updates.
6. As a developer, I want to validate payment data before submission so that I reduce gateway errors.
7. As a developer, I want to handle gateway timeouts and errors gracefully so that I maintain system reliability.
8. As a developer, I want to log payment transactions for auditing so that I can track financial activity.
9. As a developer, I want to test error conditions and edge cases so that I ensure robust integration.
10. As a developer, I want to document the payment integration so that other team members can understand and maintain it.

## 12. Good Approach

- Always split with the goal of delivering user value in each piece
- Focus on creating independent stories when possible
- Use vertical slicing to deliver end-to-end functionality (all layers)
- Consider the user journey or workflow as a splitting guide
- Split by user role or permission level when appropriate
- Break by data types or entity boundaries
- Separate simple cases from complex or edge cases
- Split by operational boundaries (create, read, update, delete)
- Consider performance or scalability concerns as splitting factors
- Split by input method or channel (web, mobile, API)
- Use the "happy path" as a first slice, then add variations
- Split by business rule variations or conditions
- Separate UI/UX concerns from core functionality when helpful
- Ensure each split story has clear acceptance criteria
- Maintain traceability from split stories back to the original epic
- Consider how split stories will be tested individually and collectively

## 13. Bad Approach

- Splitting purely by technical layers (database, API, UI) without user value
- Creating stories that are still too large for a sprint
- Making splits that create unnecessary dependencies or blocking
- Splitting in ways that lose the coherence or completeness of user value
- Creating stories that overlap significantly in functionality
- Splitting without considering testability or quality assurance
- Making splits that are impossible to demonstrate or validate independently
- Creating stories that are actually tasks rather than user-facing features
- Splitting that results in stories with no clear user benefit
- Ignoring non-functional requirements in the splitting process
- Creating splits that increase overall complexity rather than reducing it
- Forgetting to update estimates and priorities after splitting
- Losing sight of the epic's overall goal when focusing on splits

## 14. Common Mistakes

- Splitting by architectural layers instead of user value
- Creating "zombie" stories that have no value on their own
- Forgetting to split acceptance criteria along with the story
- Making uneven splits where one story gets most of the value
- Not considering the order in which split stories should be implemented
- Over-splitting to the point where overhead exceeds benefit
- Under-splitting leaving stories still too large
- Splitting without consulting the development team
- Forgetting to update story points or estimates after splitting
- Creating splits that violate the INVEST criteria
- Not documenting the rationale for how and why splits were made
- Losing track of which stories belong to which epic
- Splitting in ways that create artificial boundaries or constraints

## 15. Security Considerations

When splitting stories, consider:
- How authentication and authorization requirements distribute across splits
- Whether security controls need to be in place early or can be added later
- How data protection requirements apply to each split story
- Whether splitting creates opportunities for security vulnerabilities
- How input validation and sanitization should be handled across splits
- Whether audit logging requirements need consideration in each split
- How secrets management or credential handling should be split
- Whether security testing requirements should be considered for each split
- How compliance requirements (GDPR, HIPAA, PCI-DSS) distribute across splits
- Whether threat modeling should be reconsidered after splitting
- How security monitoring and alerting should work across split stories

## 16. Performance Considerations

Consider:
- How performance requirements distribute across split stories
- Whether performance baselines should be established early
- How caching strategies should be considered in splitting
- Whether database indexing needs affect how stories are split
- How load testing considerations should distribute across splits
- Whether resource allocation or quotas need consideration in splits
- How response time requirements should be allocated across splits
- Whether scalability concerns should influence splitting decisions
- How performance monitoring should work across split stories
- Whether capacity planning needs affect how stories are split
- How network utilization or bandwidth considerations distribute
- Whether content delivery or caching strategies affect splitting

## 17. Scalability Considerations

Think about:
- How horizontal splitting strategies affect scalability
- Whether data partitioning strategies should influence story splits
- How microservices or service boundaries might affect splitting
- Whether event-driven architectures change how stories should be split
- How state management considerations distribute across split stories
- Whether caching invalidation strategies need consideration in splits
- How API rate limiting or throttling should be handled across splits
- Whether analytical or reporting requirements affect splitting decisions
- How geographic distribution requirements influence story splits
- Whether multi-tenancy considerations should affect how stories are split
- How background job or queue processing should be split
- Whether eventual consistency concerns affect splitting strategies

## 18. Maintainability Considerations

Consider:
- How technical debt might accumulate as a result of splitting
- Whether code duplication risks increase or decrease with splitting
- How modularity and coupling considerations affect splitting decisions
- Whether abstraction opportunities become clearer after splitting
- How documentation and knowledge transfer needs distribute across splits
- Whether test maintenance considerations should influence splitting
- How observability and monitoring requirements distribute across splits
- Whether configuration management needs should be considered in splits
- How extensibility and flexibility considerations affect splitting
- Whether coding standards and practices should be consistent across splits
- How refactoring needs might emerge from the splitting process
- Whether architectural decisions should be revisited after splitting

## 19. Junior Developer Approach

Junior developers typically:
- Focus on technical boundaries rather than user value when splitting
- Create splits that are still too large or complex
- Forget to consider user experience consistency across splits
- Make splits that create unnecessary technical dependencies
- Have difficulty thinking in terms of incremental value delivery
- Struggle to identify appropriate splitting dimensions
- Tend to split evenly rather than by value or priority
- Need guidance on how to write good acceptance criteria for split stories
- Benefit from concrete examples and templates when learning
- Often overlook non-functional requirements in the splitting process
- May create splits that are actually technical tasks rather than user stories

## 20. Senior Developer Approach

Senior developers think about:
- How splitting affects the overall architecture and design
- What the optimal sequence of implementing split stories is
- How to balance upfront architectural investment with incremental delivery
- Whether splitting reveals missing requirements or design gaps
- How to preserve system integrity and coherence while splitting
- What non-functional considerations should be addressed early vs. late
- How to split stories in a way that supports future evolution
- Whether to create exploratory or prototyping splits first
- How to measure whether split stories collectively deliver epic value
- What technical risks splitting introduces and how to mitigate them
- How to balance splitting for value delivery with maintaining quality
- Whether splitting creates opportunities for better abstraction or reuse

## 21. Senior Engineer Questions

Senior engineers ask:
- "What is the minimum viable split that delivers real user value?"
- "How will we know if the split stories actually solve the original problem?"
- "What assumptions are we making about how the split stories will work together?"
- "What is the cost of coordination between split stories vs. building as a whole?"
- "Are we splitting in a way that creates technical debt we'll need to repay later?"
- "How do we ensure that performance, security, and other NFRs are addressed?"
- "What would make us realize we split this story incorrectly after implementation?"
- "How does splitting affect our ability to change or refactor the solution later?"
- "What metrics should we use to validate that split stories work together correctly?"
- "How should we handle shared components or infrastructure across split stories?"
- "Are we splitting for the right reasons (value, risk, learning) or just to fit in a sprint?"
- "What would be the consequences if we didn't split this story at all?"

## 22. Practical Exercise

**Exercise**: Split the following epic into smaller user stories:

**Epic**: As a hotel guest, I want to use the hotel's mobile app to manage my stay so that I can have a convenient, contactless experience from check-in to check-out.

For this epic:
1. Identify 5-8 distinct user goals or capabilities within this epic
2. For each goal, write a properly formatted user story
3. Define 2-3 acceptance criteria for each story using Given/When/Then format
4. Consider what order these stories should be implemented in and why
5. Identify any dependencies between the split stories
6. Note any non-functional requirements (security, performance, etc.) that should be considered
7. Suggest which stories might be good candidates for an MVP (minimum viable product)

## 23. Definition of Done

A story splitting effort is considered complete when:
- [ ] The original epic has been replaced by smaller, valuable stories
- [ ] Each split story follows the standard user story format
- [ ] Each split story has clear, testable acceptance criteria
- [ ] Each split story is small enough to fit within a sprint
- [ ] Each split story delivers identifiable user value
- [ ] Split stories are independent or have identified dependencies
- [ ] The collective value of split stories equals or exceeds the original epic
- [ ] Non-functional requirements have been considered in the splitting
- [ ] The team agrees the split stories are ready for prioritization and planning
- [ ] Estimates have been assigned to each split story (if using estimation)
- [ ] The splitting rationale has been documented for future reference
- [ ] Traceability from split stories back to the original epic is maintained
- [ ] Split stories can be tested individually and collectively

## 24. Checklist

- [ ] Does each split story represent a distinct user goal or capability?
- [ ] Does each split story follow the INVEST criteria (Independent, Negotiable, Valuable, Estimable, Small, Testable)?
- [ ] Does each split story have clear user value expressed in the "so that" clause?
- [ ] Are acceptance criteria defined for each split story?
- [ ] Are split stories small enough to complete within one sprint?
- [ ] Have we considered the order in which split stories should be implemented?
- [ ] Have we identified any dependencies between split stories?
- [ ] Have we considered non-functional requirements (performance, security, etc.)?
- [ ] Does the collection of split stories fully address the original epic's purpose?
- [ ] Have we avoided splitting purely by technical layers without user value?
- [ ] Have we ensured that split stories don't create unnecessary overlap or redundancy?
- [ ] Have we considered how split stories will be tested individually and collectively?
- [ ] Have we updated estimates and priorities for the new split stories?
- [ ] Have we documented the rationale for how and why we split the epic?
- [ ] Is traceability maintained from split stories back to the original epic?
- [ ] Would the product owner agree that these split stories represent the same epic?

## 25. Related Topics

- Related to: 01-USER-STORY-FUNDAMENTALS.md (basics), 02-USER-STORY-FORMAT.md (story format), 03-ACCEPTANCE-CRITERIA.md (acceptance criteria)
- Builds upon: Agile principles, user story mapping, backlog refinement, Minimum Viable Product (MVP) concept
- Enables: Effective sprint planning, continuous delivery, predictable velocity, incremental feedback
- Related to: User story mapping, feature breakdown, work decomposition, progressive elaboration, rolling wave planning, decomposition techniques