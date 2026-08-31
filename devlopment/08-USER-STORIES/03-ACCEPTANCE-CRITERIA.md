# 03 — ACCEPTANCE CRITERIA

## 1. What Is This?

Acceptance criteria are specific, testable conditions that a user story must satisfy to be accepted by the product owner or stakeholders. They define the boundaries of the story and confirm when it is working as intended, serving as the "Confirmation" in the 3 C's framework (Card, Conversation, Confirmation).

## 2. Why Does It Matter?

Acceptance criteria matter because they:
- Provide clarity on what "done" means for a story
- Enable objective testing and verification
- Prevent misunderstandings between developers and stakeholders
- Support automation of acceptance tests
- Help estimate effort more accurately
- Define the scope boundaries of a story
- Serve as a contract between the team and product owner
- Facilitate demos and reviews at the end of a sprint

## 3. What Problem Does It Solve?

Without clear acceptance criteria, teams experience:
- Ambiguity about when a story is complete
- Scope creep during development
- Mismatched expectations between what was built and what was wanted
- Difficulty in testing and verification
- Rework due to misunderstood requirements
- Challenges in demonstrating completion to stakeholders
- Inconsistent quality across stories
- Difficulty in automating tests

## 4. When Should We Use It?

Use acceptance criteria when:
- Defining user stories for development
- Stories need to be tested and verified
- Multiple people will work on or review the story
- Consistency and repeatability are important
- Automated testing is desired
- Regulatory or compliance verification is needed
- Stories are complex enough to benefit from explicit conditions
- Working in environments that require audit trails

## 5. When Should We NOT Use It?

Consider minimising or avoiding detailed acceptance criteria when:
- Writing spikes or exploration stories where the goal is learning
- Extremely small, trivial changes where overhead outweighs benefit
- Early-stage concepts that are intentionally vague to encourage exploration
- Work that is inherently exploratory or research-oriented
- Situations where the cost of writing and maintaining criteria exceeds benefit
- Very mature teams with shared understanding who prefer lighter documentation
- Stories that are placeholders for future detailed work

## 6. Core Concepts

### Given/When/Then Format
The most common structured format for acceptance criteria:
```
Given [context or precondition],
When [action or event],
Then [expected outcome].
```

### Alternative Formats
- **Verification Checklist**: Simple list of conditions that must be true
- **Rules Format**: "The system shall..." statements
- **Custom Formats**: Domain-specific languages or templates
- **Scenario Outline**: For data-driven testing with examples

### Characteristics of Good Acceptance Criteria
- **Testable**: Can be verified objectively
- **Clear**: Unambiguous and understandable
- **Concise**: To the point without unnecessary detail
- **Relevant**: Directly related to the user story
- **Feasible**: Possible to implement within constraints
- **Necessary**: Each criterion adds value
- **Independent**: Can be tested separately when possible
- **Traceable**: Can be linked back to requirements or goals

### Levels of Acceptance Criteria
- **Story-level**: Specific to a single user story
- **Epic-level**: Apply to all stories in an epic
- **Release-level**: Apply to an entire release
- **Global/Non-functional**: Apply across multiple stories (performance, security, etc.)

## 7. Step-by-Step Process

1. **Understand the story**: Ensure you grasp the user's goal and value
2. **Identify success conditions**: What must be true for the user to be satisfied?
3. **Consider edge cases**: What unusual situations might arise?
4. **Think about error conditions**: What could go wrong and how should it be handled?
5. **Write in Given/When/Then format**: Structure each criterion clearly
6. **Review for testability**: Can each criterion be objectively verified?
7. **Check for completeness**: Do criteria cover the full scope of the story?
8. **Validate with stakeholders**: Ensure product owner agrees these define "done"
9. **Refine based on feedback**: Update criteria as understanding evolves
10. **Use for test creation**: Convert criteria into test cases

## 8. Inputs

Inputs to creating acceptance criteria include:
- The user story itself (role, goal, benefit)
- User research and persona insights
- Business rules and policies
- Technical constraints and considerations
- Previous similar stories or features
- Regulatory or compliance requirements
- Usability and accessibility guidelines
- Performance and security requirements
- Stakeholder expectations and feedback
- Data requirements and constraints
- Integration points with other systems

## 9. Outputs / Deliverables

Outputs from defining acceptance criteria include:
- Clear, testable conditions for each user story
- Basis for creating test cases (manual and automated)
- Definition of when a story is complete
- Shared understanding between team and product owner
- Input for sprint planning and estimation
- Foundations for automated acceptance testing
- Documentation for compliance and audit purposes
- Reference for demos and sprint reviews
- Input for definition of done checks

## 10. Real-World Example

**User Story**:
```
As a bank customer,
I want to transfer money between my accounts,
so that I can manage my finances efficiently.
```

**Acceptance Criteria**:
```
Given I am logged into the banking app,
And I have at least two accounts with sufficient funds,
When I initiate a transfer from Account A to Account B,
Then the transfer should be processed immediately
And Account A balance should decrease by the transfer amount
And Account B balance should increase by the transfer amount
And I should receive a confirmation notification
And the transaction should appear in both accounts' history

Given I attempt to transfer more than my available balance,
When I submit the transfer request,
Then I should see an error message about insufficient funds
And the transfer should not be processed
And neither account balance should change

Given I am not logged in,
When I try to access the transfer function,
Then I should be redirected to the login page
```

## 11. Technical Example

**User Story**:
```
As an API developer,
I want to authenticate using OAuth 2.0 client credentials flow,
so that I can securely access protected API resources without user interaction.
```

**Acceptance Criteria**:
```
Given valid client ID and client secret,
When I request an access token from the token endpoint,
Then I should receive a valid access token
And the token type should be "Bearer"
And the expires_in value should be a positive integer
And the scope should match the requested scope

Given invalid client credentials,
When I request an access token,
Then I should receive an HTTP 401 Unauthorized response
And the error response should include "invalid_client" error code

Given an expired access token,
When I attempt to access a protected resource,
Then I should receive an HTTP 401 Unauthorized response
And the WWW-Authenticate header should indicate token expiration

Given a valid access token,
When I make a request to a protected endpoint with proper scopes,
Then I should receive a successful response (2xx)
And the response data should match the expected format

Given a valid access token,
When I make a request to an endpoint outside the token's scope,
Then I should receive an HTTP 403 Forbidden response
```

## 12. Good Approach

- Write criteria from the user's perspective, not technical implementation
- Focus on observable outcomes, not internal processes
- Include both positive (happy path) and negative (error) cases
- Consider edge cases and boundary conditions
- Use clear, unambiguous language
- Make each criterion independently testable when possible
- Align criteria with the story's stated value ("so that...")
- Keep criteria at the right level of detail (not too vague, not overly prescriptive)
- Involve the team in reviewing criteria for feasibility and testability
- Update criteria as understanding evolves during development
- Use the Given/When/Then format consistently for readability
- Ensure criteria are small enough to be meaningful but not overly granular

## 13. Bad Approach

- Writing criteria that describe implementation details
- Creating criteria that cannot be tested objectively
- Making criteria too vague ("system should be user-friendly")
- Writing criteria that are actually tasks or technical steps
- Forgetting error handling and edge cases
- Creating an excessive number of trivial criteria
- Writing criteria that duplicate or contradict each other
- Making criteria dependent on unspecified external factors
- Writing criteria that are true by definition (tautologies)
- Including non-testable qualities without clear metrics
- Writing criteria that belong in non-functional requirements rather than the story
- Creating criteria that require impossible or prohibitively expensive testing

## 14. Common Mistakes

- Confusing acceptance criteria with task lists or technical specifications
- Writing criteria that are too broad to be useful ("system should work correctly")
- Omitting criteria for error conditions and edge cases
- Making assumptions about user behavior or environment
- Writing criteria that are impossible to test in a reasonable timeframe
- Creating criteria that change frequently without reason
- Not involving QA or testing perspectives when writing criteria
- Using passive voice that obscures responsibility ("it should be done")
- Forgetting to consider data validation and sanitization
- Neglecting to specify expected performance or response times
- Writing criteria that assume a specific UI implementation
- Creating criteria that are actually non-functional requirements in disguise

## 15. Security Considerations

When writing acceptance criteria, consider:
- Authentication requirements: Who can access this functionality?
- Authorization checks: What roles or permissions are needed?
- Input validation: How are inputs validated to prevent injection attacks?
- Data protection: How is sensitive data handled in transit and at rest?
- Session management: How are sessions created, maintained, and terminated?
- Error handling: Do error messages leak sensitive information?
- Logging and auditing: Are security-relevant events logged appropriately?
- Encryption: Is data encrypted where required by policy or regulation?
- Secure defaults: Are secure settings used unless explicitly overridden?
- Third-party components: Are dependencies checked for known vulnerabilities?
- Security testing: Can security criteria be validated through testing?

## 16. Performance Considerations

Consider:
- Response time expectations: How quickly should the system respond?
- Throughput requirements: How many transactions per second are needed?
- Resource usage: What are acceptable levels of CPU, memory, or storage use?
- Scalability: How should performance behave under increasing load?
- Latency: What are acceptable delays for different types of operations?
- Capacity: What are the maximum user volumes or data sizes supported?
- Degradation: How should the system behave when limits are approached?
- Monitoring: What performance metrics should be collected and alerted on?
- Caching: Are caching strategies appropriate and effective?
- Database queries: Are queries optimized and indexed properly?
- Network usage: Are unnecessary network calls avoided?

## 17. Scalability Considerations

Think about:
- Horizontal scaling: Can the solution work across multiple instances?
- Data partitioning: How will data be distributed as it grows?
- Caching strategies: What caching approaches will scale effectively?
- Database design: Will current database choices support growth?
- Asynchronous processing: Should long-running tasks be decoupled?
- Message queuing: Is messaging infrastructure appropriate for scale?
- Load balancing: Will traffic distribution work effectively at scale?
- Geographic distribution: Will users in different locations have good performance?
- Multi-tenancy: If applicable, how will isolation and resource sharing work?
- Caching invalidation: How will cached data stay consistent as data changes?
- Bottleneck identification: Where might performance constraints emerge as load increases?

## 18. Maintainability Considerations

Consider:
- Code simplicity: Is the implementation straightforward to understand?
- Coupling: Does this create unnecessary dependencies between components?
- Cohesion: Does the implementation stay focused on a single responsibility?
- Duplication: Are we repeating logic that should be abstracted?
- Testability: Is the code easy to unit test and mock?
- Observability: Can we monitor and debug this implementation effectively?
- Extensibility: Will it be easy to add features or modify behavior later?
- Standards compliance: Does it follow established coding standards and patterns?
- Dependency management: Are external dependencies appropriate and managed?
- Documentation: Will future developers understand why it was built this way?
- Technical debt: Are we taking shortcuts that will need to be repaid later?
- Reversibility: Can changes be rolled back if needed?

## 19. Junior Developer Approach

Junior developers typically:
- Write acceptance criteria that are too vague or general
- Focus only on the happy path and forget error conditions
- Include implementation details in acceptance criteria
- Make criteria impossible to test objectively
- Create an excessive number of overly granular criteria
- Have difficulty thinking from the user's perspective
- Struggle with edge cases and boundary conditions
- Write criteria that are actually tasks or technical steps
- Need examples and practice to understand what makes good criteria
- Benefit from templates and checklists when getting started
- Often write criteria that sound like requirements documents rather than test conditions

## 20. Senior Developer Approach

Senior developers think about:
- How acceptance criteria will be tested (manually vs. automated)
- What test data or test environments will be needed
- Whether criteria are at the right level of abstraction
- How to balance specificity with flexibility in implementation
- What non-functional requirements should be called out explicitly
- How to write criteria that withstand implementation changes
- Whether criteria reveal missing dependencies or architectural gaps
- How to split complex criteria into independently testable units
- How to validate that criteria actually measure the intended outcome
- The trade-off between precision and feasibility in testing
- How criteria relate to the definition of done for the sprint or release
- Whether automation of certain criteria would provide long-term value

## 21. Senior Engineer Questions

Senior engineers ask:
- "What is the minimum set of criteria that would give us confidence this works?"
- "How would we know if we built the wrong thing even if all criteria pass?"
- "What assumptions are baked into these criteria that might not hold?"
- "How expensive or difficult will it be to verify each criterion?"
- "Could we achieve the same validation with fewer, smarter criteria?"
- "What would make us realize these criteria are inadequate after release?"
- "How do these criteria affect our ability to change or refactor later?"
- "Are we testing the right things, or just what's easy to test?"
- "What non-functional aspects should be elevated to explicit criteria?"
- "How do these criteria interact with acceptance criteria from related stories?"
- "What measurement approaches would validate these criteria in production?"
- "Are we writing criteria to pass tests, or to ensure real user value?"

## 22. Practical Exercise

**Exercise**: Write acceptance criteria for the following user stories:

1. **Story**: As a frequent traveler, I want to receive flight delay notifications so that I can adjust my travel plans accordingly.
2. **Story**: As an online shopper, I want to save items to a wish list so that I can purchase them later.
3. **Story**: As a gym member, I want to book personal training sessions online so that I can schedule workouts around my availability.
4. **Story**: As a customer service agent, I want to view a customer's complete interaction history so that I can provide personalized support.

For each story:
1. Write 3-5 acceptance criteria in Given/When/Then format
2. Include both positive (happy path) and negative/error cases
3. Consider at least one edge case or boundary condition
4. Think about any security, performance, or usability considerations
5. Ensure criteria are testable and objectively verifiable
6. Note which criteria might be good candidates for automation

## 23. Definition of Done

Acceptance criteria are considered complete when:
- [ ] Each criterion is written in clear, unambiguous language
- [ ] Criteria are testable and can be objectively verified
- [ ] Both positive (happy path) and negative cases are covered
- [ ] Edge cases and boundary conditions are considered
- [ ] Criteria focus on outcomes, not implementation details
- [ ] Each criterion is independent enough to be tested separately
- [ ] Language is concise and free of unnecessary detail
- [ ] Criteria are understandable to both technical and non-technical stakeholders
- [ ] Criteria align with and support the user story's stated value
- [ ] The team agrees these criteria define when the story is done
- [ ] Criteria have been reviewed for feasibility and testability
- [ ] Any non-functional requirements implied by the story are addressed
- [ ] Criteria are small enough to be meaningful but not overly granular

## 24. Checklist

- [ ] Does each criterion start with Given, When, Then (or equivalent structure)?
- [ ] Are criteria written from the user's or system's observable behavior perspective?
- [ ] Do criteria avoid describing how the system works internally?
- [ ] Are both success and failure scenarios included?
- [ ] Have edge cases (empty data, maximum values, etc.) been considered?
- [ ] Are criteria free of implementation or technical specifics?
- [ ] Is each criterion focused on a single, verifiable outcome?
- [ ] Can each criterion be tested without needing others to pass first?
- [ ] Is the language unambiguous and clear to all stakeholders?
- [ ] Do criteria collectively define a complete picture of "done" for this story?
- [ ] Have we considered performance or response time expectations?
- [ ] Have we considered security or authentication requirements?
- [ ] Have we considered usability or accessibility aspects?
- [ ] Are criteria written in present tense?
- [ ] Do criteria avoid words like "should" or "must" in favor of definitive statements?
- [ ] Would a tester be able to determine pass/fail without clarification?
- [ ] Have we considered data validation and error handling scenarios?
- [ ] Are any criteria actually non-functional requirements that should be elevated?
- [ ] Is the number of criteria appropriate (neither too few nor too many)?

## 25. Related Topics

- Related to: 01-USER-STORY-FUNDAMENTALS.md (basics), 02-USER-STORY-FORMAT.md (story format), 04-STORY-SPLITTING.md (breaking down large stories)
- Builds upon: Agile testing principles, Behavior-Driven Development (BDD), Specification by Example
- Enables: Test automation, sprint reviews, objective completion measurement, regression testing
- Related to: Definition of Done, test cases, test plans, verification and validation, quality assurance, Given/When/Then, Gherkin syntax, Cucumber, SpecFlow