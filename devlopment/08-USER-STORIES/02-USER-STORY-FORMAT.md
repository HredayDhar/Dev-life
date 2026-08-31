# 02 — USER STORY FORMAT

## 1. What Is This?

The user story format is a standardized template for writing user stories that ensures consistency, clarity, and focus on user value. While variations exist, the most common format follows the "As a [role], I want [goal] so that [benefit]" structure.

## 2. Why Does It Matter?

A consistent format matters because it:
- Ensures all critical elements (who, what, why) are present
- Makes stories easy to read and understand at a glance
- Helps teams quickly identify missing information
- Supports tooling and automation in Agile lifecycle management tools
- Creates a shared understanding across distributed teams
- Prevents omission of the value component, which is often forgotten

## 3. What Problem Does It Solve?

Without a standard format, teams often encounter:
- Incomplete stories missing key components
- Inconsistent wording that creates confusion
- Overly technical descriptions that lose user focus
- Vague or ambiguous requirements
- Difficulty comparing or prioritizing stories
- Lost context when stories are handed off between team members

## 4. When Should We Use It?

Use the standard user story format when:
- Working in Agile environments (Scrum, Kanban, etc.)
- Collaborating with cross-functional teams
- Stories will be tracked in digital tools (Jira, Azure DevOps, etc.)
- Multiple people will write or review stories
- Stories need to be understood by both technical and non-technical stakeholders
- Consistency across a large backlog is important
- Training new team members on story writing

## 5. When Should We NOT Use It?

Consider alternatives when:
- Working with highly technical audiences who prefer task-oriented descriptions
- Writing spikes or research stories where the goal is learning, not delivery
- Creating very small improvements where overhead outweighs benefit
- Working in environments that mandate different formats (e.g., use cases)
- Writing non-functional requirements or quality attributes
- Creating architectural decisions that affect multiple user stories

## 6. Core Concepts

### Standard Format Template
```
As a [role or persona],
I want [goal or desire],
so that [benefit or value].
```

### Components Explained
- **Role/Persona**: Who wants this? (Specific user type, not "user" or "system")
- **Goal/Desire**: What does the user want to accomplish? (Action-oriented)
- **Benefit/Value**: Why does the user want this? (Business value, user outcome)

### Variations
While the standard format is most common, variations include:
- **As a [role], I want [goal]**: Used when the benefit is obvious
- **In order to [benefit], as a [role], I want [goal]**: Puts value first
- **As [role], I can [goal]**: Used for capabilities rather than desires
- **[Role] needs to [goal] to achieve [benefit]**: More natural language variant

### Acceptance Criteria Format
Often written as Given/When/Then:
```
Given [context or precondition],
When [action or event],
Then [expected outcome].
```

## 7. Step-by-Step Process

1. **Identify the user role**: Be specific (e.g., "Frequent Shopper" not "User")
2. **Define the user goal**: What action do they want to perform?
3. **Articulate the value**: Why does this matter to them or the business?
4. **Write in standard format**: Fill in the three components
5. **Review for completeness**: Ensure all three parts are present
6. **Check for user focus**: Avoid technical implementation details
7. **Verify independence**: Can this story stand alone?
8. **Add acceptance criteria**: Define how we'll know it's done
9. **Review with team**: Get feedback on clarity and completeness
10. **Refine as needed**: Update based on team input

## 8. Inputs

Inputs to formatting user stories include:
- Raw ideas from brainstorming sessions
- User research insights and quotes
- Business objectives and goals
- Process improvement opportunities
- Customer feedback and support tickets
- Competitive analysis findings
- Regulatory or compliance requirements
- Technology constraints or opportunities
- Stakeholder interviews and workshops
- Existing requirements or use cases being converted

## 9. Outputs / Deliverables

Outputs from proper formatting include:
- Consistently formatted user stories
- Clear identification of user, goal, and value
- Stories ready for acceptance criteria definition
- Backlog items that can be easily compared and prioritized
- Reduced need for clarification questions during development
- Improved velocity due to better story understanding
- Enhanced traceability from business goals to implementation

## 10. Real-World Example

**Poorly formatted**: "Users need to be able to reset their passwords when they forget them"

**Well-formatted using standard template**:
```
As a registered customer,
I want to reset my password via email,
so that I can regain access to my account when I forget my password.
```

**Even better with specific persona**:
```
As a busy parent who shops online late at night,
I want to reset my password using my email address,
so that I can quickly regain access to complete my purchase without calling customer support.
```

## 11. Technical Example

For an API developer portal:
```
As an API consumer integrating with the payment service,
I want to receive webhook notifications for successful transactions,
so that I can automatically update my order management system in real time.
```

## 12. Good Approach

- Be specific about the role (avoid generic "user" or "system")
- Focus on what the user wants to do, not how the system does it
- Always include the "so that" clause to articulate value
- Use active voice and present tense
- Keep it concise but descriptive
- Make the goal achievable within one story
- Write acceptance criteria separately but consistently
- Use the team's Definition of Ready as a checklist
- When in doubt, ask: "Who specifically benefits and how?"
- Use real user quotes or research to inform role descriptions

## 13. Bad Approach

- Writing technical tasks: "Create password reset API endpoint"
- Being too vague: "As a user, I want better security"
- Forgetting the value: "As a customer, I want to reset my password"
- Using passive voice: "Password reset functionality should be provided"
- Including implementation details: "As a user, I want to click a 'Forgot Password' link that sends an email with a token"
- Being redundant: "As a customer, I want to be able to reset my password so that I can reset my password"
- Making assumptions about solution: "As a user, I want to use Google OAuth to reset my password"
- Writing stories that are actually epics: "As a user, I want all account management features"

## 14. Common Mistakes

- Using "system" or "application" as the role
- Writing the goal as a feature rather than an action
- Omitting the benefit entirely
- Making the benefit restate the goal ("so that I can [same as goal]")
- Using future tense ("I will want") or past tense ("I wanted")
- Including "and" in the goal, indicating multiple stories
- Writing stories that are too large to fit in a sprint
- Confusing user stories with use cases or technical specifications
- Forgetting that the format is a conversation starter, not a contract
- Not updating the format as the team learns what works best for them

## 15. Security Considerations

When formatting stories, consider:
- Does the role imply specific access levels or permissions?
- Does the goal involve accessing sensitive data or functions?
- Should the benefit mention security outcomes (e.g., "so that my data remains private")?
- Might this story require authentication or authorization considerations?
- Could implementing this goal introduce security vulnerabilities if not done carefully?
- Does the role need to distinguish between different user types with different access rights?

## 16. Performance Considerations

Consider:
- Does achieving this goal have performance implications?
- Should the benefit mention performance expectations?
- Might this goal require optimization for large data sets or high volume?
- Does the role represent a user segment with specific performance needs (e.g., mobile users)?
- Could the implementation approach affect system performance under load?
- Should acceptance criteria include performance benchmarks?

## 17. Scalability Considerations

Think about:
- Will this goal need to work as user numbers or data volumes grow?
- Does the role represent a growing user segment?
- Might the implementation approach need to change at scale?
- Should the benefit mention scalability outcomes?
- Will this feature need to work across multiple instances or regions?
- Could this goal create bottlenecks if not designed for scalability?
- Does the story need to consider eventual consistency or distributed systems challenges?

## 18. Maintainability Considerations

Consider:
- Will this implementation be easy to modify or extend later?
- Does following this goal create technical debt we should avoid?
- Is there a simpler way to achieve the same user goal?
- Does this goal align with architectural principles and patterns?
- Will other teams need to understand or maintain this implementation?
- Could this goal be achieved through configuration rather than code?
- Does the implementation approach follow DRY (Don't Repeat Yourself) principles?

## 19. Junior Developer Approach

Junior developers typically:
- Struggle to be specific about roles beyond generic "user"
- Forget to include the "so that" benefit component
- Write goals that describe system features rather than user actions
- Include implementation details in the goal statement
- Make stories too large or complex
- Have difficulty distinguishing between user stories and tasks
- Need examples and practice to internalize the format
- Benefit from having the format visible as a reference when writing
- Often write stories that sound like requirements documents

## 20. Senior Developer Approach

Senior developers think about:
- How the role definition affects access controls and security
- Whether the goal is truly independent or has hidden dependencies
- How the value proposition aligns with business metrics and objectives
- What non-functional requirements (performance, security, etc.) are implied
- How this story might be split to deliver value incrementally
- Whether the stated goal actually solves the user's underlying problem
- How to write acceptance criteria that are testable without being overly prescriptive
- The balance between being specific enough to be useful and general enough to allow flexibility
- How this story fits into larger epics or initiatives
- What alternative approaches might achieve the same user goal

## 21. Senior Engineer Questions

Senior engineers ask:
- "Is this role specific enough to be meaningful, or is it just a wrapper for 'user'?"
- "Does this goal describe an action the user performs, or a feature the system provides?"
- "Is the stated benefit the real reason users want this, or is there a deeper motivation?"
- "What assumptions are we making about the user's context or capabilities?"
- "How would we measure whether this story actually delivers the claimed benefit?"
- "What alternatives exist for achieving the same user goal?"
- "What would make us realize we got this story wrong after implementation?"
- "How small can we make this story while still delivering real value?"
- "What dependencies does this story have that aren't obvious from the format?"
- "How does this story affect our system's architectural integrity?"

## 22. Practical Exercise

**Exercise**: Rewrite the following poorly formatted ideas into proper user story format:

1. "Customers should be able to save items for later purchase"
2. "The system needs to export data to CSV format"
3. "Users want faster page loading times"
4. "Administrators must be able to manage user permissions"
5. "Mobile app should work offline"

For each:
1. Identify a specific user role (beyond generic "user" or "customer")
2. Articulate a clear user goal in action terms
3. Define the specific business or user value
4. Write it in standard "As a..., I want..., so that..." format
5. Note what makes this better than the original

## 23. Definition of Done

A user story is properly formatted when:
- [ ] Follows "As a [role], I want [goal] so that [benefit]" structure
- [ ] Role is specific and represents a real user type (not "user" or "system")
- [ ] Goal describes an action the user wants to perform
- [ ] Benefit articulates clear value or outcome (not just restating the goal)
- [ ] Written in active voice, present tense
- [ ] Free of implementation or technical details
- [ ] Concise enough to be easily readable (typically one sentence per component)
- [ ] Focused on a single, achievable user goal
- [ ] Ready for acceptance criteria to be added
- [ ] Understandable to both technical and non-technical stakeholders

## 24. Checklist

- [ ] Does it start with "As a"?
- [ ] Is the role specific and meaningful (not "user", "system", or "application")?
- [ ] Does it contain "I want" after the role?
- [ ] Does the goal describe an action, not a feature or system capability?
- [ ] Does it contain "so that" after the goal?
- [ ] Does the benefit explain why this matters (value, outcome, result)?
- [ ] Is the benefit distinct from the goal (not just repeating it)?
- [ ] Is the story written in present tense?
- [ ] Is the story free of technical implementation details?
- [ ] Does it avoid words like "should", "must", or "needs to" in favor of direct statement?
- [ ] Is the goal achievable within one story (not overly broad)?
- [ ] Would the intended user recognize this as something they actually want?
- [ ] Is the language clear and free of jargon (unless the user is technical)?
- [ ] Does the story pass the "so what?" test (clear why it matters)?

## 25. Related Topics

- Related to: 01-USER-STORY-FUNDAMENTALS.md (basics), 03-ACCEPTANCE-CRITERIA.md (acceptance criteria format), 04-STORY-SPLITTING.md (breaking down large stories)
- Builds upon: Agile Manifesto principles, user-centered design, INVEST criteria
- Enables: Effective backlog grooming, sprint planning, estimation, automated tool processing
- Related to: Conversation over documentation, 3 C's (Card, Conversation, Confirmation), User Story Mapping, Specification by Example, Given/When/Then format