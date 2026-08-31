# 02 — FUNCTIONAL REQUIREMENTS

## 1. What Are Functional Requirements?

Functional requirements describe what a system should do—its specific behaviors, functions, and capabilities. They define the specific actions the system must perform in response to inputs, the operations it must execute, and the outputs it must produce. Functional requirements answer the question: "What functions must the system perform to satisfy user needs and business objectives?"

Unlike non-functional requirements (which describe how well the system performs), functional requirements focus on the system's core functionality. They are typically expressed as actions or services the system provides and are directly testable through execution of specific scenarios.

## 2. Characteristics of Effective Functional Requirements

Effective functional requirements share several key characteristics that make them useful for development, testing, and validation:

### Action-Oriented
Functional requirements describe actions, behaviors, or processes—not states or qualities.

**Weak**: "The system should be capable of processing orders"
**Strong**: "The system shall process customer orders by validating items, calculating totals, applying discounts, and generating invoices"

### Singular Focus
Each requirement should address one specific function or behavior to avoid ambiguity and simplify testing.

**Weak**: "The system shall allow users to search for products and view detailed product information"
**Strong**: 
- "The system shall allow users to search for products by keyword, category, or price range"
- "The system shall display detailed product information when a user selects a product from search results"

### Clear Actor and Action
Effective functional requirements clearly identify who or what initiates the action and what action is performed.

**Format**: "[Actor] shall [action] [object] under [conditions]"

**Examples**:
- "The customer shall be able to reset their password via email verification"
- "The system shall notify the inventory manager when stock levels fall below threshold"
- "The administrator shall be able to configure tax rates for different jurisdictions"

### Measurable Outcomes
Functional requirements should specify observable, measurable outcomes that indicate successful completion.

**Weak**: "The system should provide fast search results"
**Strong**: "The system shall return search results within 2 seconds for queries matching fewer than 10,000 records"

### Unambiguous Language
Requirements must be interpretable in only one way by reasonable readers with relevant expertise.

**Ambiguous**: "The system should handle high volumes of traffic efficiently"
**Unambiguous**: "The system shall process up to 1,000 transactions per minute with 99.9% success rate"

### Completeness
Each functional requirement should contain all necessary information to understand and implement the function without requiring additional clarification.

**Incomplete**: "The system shall process returns"
**Complete**: "The system shall process customer returns for items purchased within the last 30 days, provided the item is in resalable condition and accompanied by original receipt"

### Traceability
Functional requirements should be traceable to their origins (user needs, business goals, regulations) and forward to design elements, test cases, and other artifacts.

### Consistency
Functional requirements should not contradict each other or create impossible combinations when implemented together.

## 3. Formats for Expressing Functional Requirements

### Traditional "Shall" Statements
Common in regulated industries and waterfall projects, using the format: "The system shall [action] [object] under [conditions]."

**Structure**:
- **Subject**: Typically "The system" or a specific subsystem
- **Verb**: "shall" indicating mandatory requirement
- **Action**: What the system does
- **Object**: What the action is performed on
- **Conditions**: Constraints, triggers, or qualifiers (optional but often included)

**Examples**:
- "The system shall encrypt all personally identifiable information using AES-256 encryption"
- "The system shall allow customers to place items in a shopping cart"
- "The system shall calculate shipping costs based on destination address and package weight"
- "The system shall send order confirmation emails within 5 minutes of purchase completion"
- "The system shall display real-time inventory levels for products in the warehouse"

**Advantages**:
- Precise and unambiguous when well-written
- Easy to trace and manage
- Familiar to auditors and regulators
- Good for complex systems with many detailed requirements

**Disadvantages**:
- Can be verbose and repetitive
- May encourage over-specification of solutions
- Less engaging for business stakeholders
- Can obscure the user perspective

### User Stories
Popular in agile methodologies, following the template: "As a [role], I want [goal] so that [benefit]."

**Components**:
- **Role**: The type of user who wants the feature (specific, not generic)
- **I want**: The capability or functionality desired
- **So that**: The value, benefit, or reason for wanting it

**Examples**:
- "As a customer, I want to save items to a wish list so I can purchase them later"
- "As a library patron, I want to renew borrowed books online so I don't need to visit the library in person"
- "As a warehouse supervisor, I want to scan barcodes with a mobile device so I can update inventory counts in real time"
- "As a travel agent, I want to book multi-city itineraries so I can serve clients with complex travel plans"
- "As a patient, I want to message my doctor through the portal so I can get quick answers to non-urgent questions"

**Acceptance Criteria**: Specific conditions that must be met for the story to be considered complete, typically written in Given/When/Then format:
- **Given**: Preconditions or initial state
- **When**: Action or event that triggers the behavior
- **Then**: Expected outcome or result

**Example Acceptance Criteria for wish list story**:
- Given: Authenticated user browsing product catalog
- When: User clicks "Save to Wish List" button on product page
- Then: Product is added to user's wish list
- And: Wish list count updates in navigation menu
- And: User sees confirmation message "Item saved to wish list"
- Given: User viewing their wish list
- When: User clicks "Move to Cart" next to an item
- Then: Item is removed from wish list and added to shopping cart
- And: Wish list count decreases by one
- And: Shopping cart count increases by one
- Given: User has items in wish list for over 30 days
- When: User logs into their account
- Then: System displays reminder: "You have items saved in your wish list for over 30 days"

**Advantages**:
- Focuses on user value and perspective
- Encourages conversation and collaboration
- Easy for business stakeholders to understand
- Naturally prioritizes by user benefit
- Supports incremental delivery and feedback

**Disadvantages**:
- Can lack detail needed for complex functionality
- May require significant elaboration for acceptance criteria
- Less suitable for technical or system-level requirements
- Can lead to fragmented view without proper context

### Use Cases
Detailed descriptions of interactions between actors and the system to achieve a specific goal, widely used in various methodologies.

**Elements**:
- **Use Case Name**: Clear verb-noun phrase describing the goal
- **Actors**: Who or what initiates or participates (primary and secondary)
- **Stakeholders and Interests**: Who cares about this use case and what they want
- **Preconditions**: What must be true before use case can start
- **Main Flow (Basic Flow)**: Step-by-step description of typical successful sequence
- **Extensions (Alternative Paths)**: Alternative sequences (error conditions, variations, optional steps)
- **Postconditions**: What is true after use case completes successfully
- **Triggers**: What initiates the use case
- **Frequency**: How often the use case occurs
- **Priority**: Importance to stakeholders
- **Non-Functional Requirements**: Specific qualities applicable to this use case
- **Special Requirements**: Unique constraints or considerations

**Example Use Case: Process Online Order**
- **Name**: Process Customer Order Through Website
- **Primary Actor**: Customer
- **Secondary Actors**: Payment Gateway, Inventory System, Email Service
- **Stakeholders and Interests**:
  - Customer: Wants secure, accurate order processing with confirmation
  - Business: Needs accurate revenue capture and inventory deduction
  - Warehouse: Requires timely notification for fulfillment
  - Accounting: Requires proper transaction recording for financial reporting
- **Preconditions**: Customer has selected items and proceeded to checkout
- **Main Flow**:
  1. Customer enters shipping and billing information
  2. Customer selects payment method and enters payment details
  3. System validates payment information with payment gateway
  4. System verifies item availability in inventory
  5. System calculates total including tax and shipping
  6. System creates order record with pending status
  7. System charges customer's payment method via payment gateway
  8. System confirms successful payment with payment gateway
  9. System updates order status to "confirmed"
  10. System reserves items in inventory (deducts from available stock)
  11. System sends order confirmation email to customer
  12. System notifies warehouse system of new order for fulfillment
  13. System displays order confirmation page with order number
- **Extensions**:
  3a. Payment validation fails: Display error message, allow retry or alternative payment
  4a. Item out of stock: Display availability status, suggest alternatives or notify when available
  5a. Tax calculation service unavailable: Use cached rates with warning, allow manual override
  6a. System failure during order creation: Rollback any partial changes, display error
  7a. Payment gateway timeout: Retry up to 3 times, then display error
  8a. Payment declined: Display specific error based on payment gateway response
  9a. Email service unavailable: Log error, continue with order confirmation (non-blocking)
  12a. Inventory system unavailable: Log error, proceed with order (fulfillment handled manually)
- **Postconditions**: Order recorded in system, payment processed, inventory reserved, confirmation sent, warehouse notified
- **Trigger**: Customer submits checkout form
- **Frequency**: Approximately 100 orders per hour during peak periods
- **Priority**: Must have for initial release
- **Non-Functional Requirements**:
  - Performance: Complete main flow within 10 seconds 95% of time
  - Security: PCI DSS compliance for payment processing
  - Availability: 99.9% uptime for checkout function
  - Auditability: Complete transaction trail for all steps

**Advantages**:
- Provides rich context and detail
- Clearly shows user-system interactions
- Handles both normal and exceptional flows
- Supports traceability to tests (each path = test case)
- Works well for complex business logic
- Facilitates understanding of system behavior

**Disadvantages**:
- More time-consuming to write and maintain
- Can be overly detailed for simple functions
- May require significant training to write effectively
- Can become difficult to manage at scale
- Risk of focusing too much on interface details

### Scenarios and Examples
Concrete illustrations of how the system should behave in specific situations.

**Characteristics**:
- Specific, detailed instances rather than generalizations
- Include inputs, actions, and expected outputs
- Useful for clarifying ambiguous requirements
- Effective for demonstrating edge cases and error handling
- Complement other requirement formats

**Example Scenario: Applying Discount Codes**
- **Scenario**: Customer applies valid promotional code during checkout
  - Given: Customer has items in cart totaling $100
  - When: Customer enters valid promo code "SAVE10" and clicks "Apply"
  - Then: System validates code is active and applicable to cart items
  - And: System calculates 10% discount ($10) on eligible items
  - And: System displays updated cart total of $90
  - And: System shows applied discount breakdown in order summary
  - And: System stores discount code with order for fulfillment tracking

- **Scenario**: Customer attempts to use expired promotional code
  - Given: Customer has items in cart totaling $50
  - When: Customer enters expired promo code "OLD20" and clicks "Apply"
  - Then: System validates code and determines it expired on 2026-01-01
  - And: System displays error message: "Promo code OLD20 has expired"
  - And: System does not modify cart total or apply any discount
  - And: System allows customer to continue with checkout using original total

- **Scenario**: Customer tries to use code for ineligible items
  - Given: Cart contains $30 of eligible items and $20 of excluded items
  - When: Customer enters promo code "SPECIAL15" valid only for category "Books"
  - Then: System validates code applicability to each cart item
  - And: System applies 15% discount only to $30 of eligible items ($4.50 discount)
  - And: System displays cart total of $45.50 ($50 - $4.50)
  - And: System shows discount applied only to book items in breakdown

**Advantages**:
- Extremely concrete and easy to understand
- Excellent for clarifying complex business rules
- Effective for demonstrating edge cases
- Helpful in requirements validation sessions
- Natural format for acceptance testing

**Disadvantages**:
- Not suitable as sole specification method (too many needed for complete coverage)
- Can be redundant if overused
- Difficult to maintain consistency across many scenarios
- May miss general patterns or principles

### Decision Tables and Trees
Structured formats for representing complex business logic with multiple conditions and actions.

**Decision Table Structure**:
- **Conditions**: Inputs or states that determine outcome
- **Actions**: System responses or behaviors based on condition combinations
- **Rules**: Specific combinations of conditions and resulting actions

**Example: Loan Approval Decision Table**
| Conditions                | Rule 1 | Rule 2 | Rule 3 | Rule 4 | Rule 5 |
|---------------------------|--------|--------|--------|--------|--------|
| Credit Score ≥ 700        | T      | T      | F      | F      | F      |
| Income ≥ $50,000          | T      | F      | T      | F      | F      |
| Debt-to-Income ≤ 0.4      | T      | T      | T      | F      | F      |
| Employment ≥ 2 years      | T      | T      | T      | T      | F      |
| **Actions**               |        |        |        |        |        |
| Approve Loan              | X      |        |        |        |        |
| Approve with Higher Rate  |        | X      | X      |        |        |
| Require Cosigner          |        |        |        | X      |        |
| Reject Application        |        |        |        |        | X      |

**Decision Tree Structure**:
- Nodes represent conditions or decisions
- Branches represent outcomes of those decisions
- Leaf nodes represent final actions or results

**Example: Shipping Method Selection Decision Tree**
```
Start
│
├─ Package Weight > 50 lbs? ─No─┐
│                              │
│         Destination International? ─No─► Standard Ground (3-5 days)
│                              │
│                              ├─Yes─► International Air (7-14 days)
│
├─Yes─► Freight Quote Required
│                │
│                ├─ Customer Accepts Quote? ─No─► Cancel Order
│                │
│                └─Yes─► Schedule Freight Pickup
```

**Advantages**:
- Excellent for complex business logic with multiple conditions
- Clearly shows all possible combinations and outcomes
- Easy to verify completeness and consistency
- Natural translation to implementation (case statements, polymorphism)
- Reduces ambiguity in conditional requirements

**Disadvantages**:
- Can become very large and complex for many conditions
- Less intuitive for business stakeholders unfamiliar with format
- May overspecify implementation approach
- Difficult to represent temporal aspects or sequences

## 4. Techniques for Eliciting and Writing Functional Requirements

### Interviewing Techniques
Effective conversations to uncover functional needs.

**Preparation**:
- Research stakeholder role and responsibilities
- Prepare open-ended questions focused on goals and tasks
- Define specific objectives for the interview
- Plan for documentation (recording, notes, or both)
- Consider sending questions in advance for preparation

**Execution**:
- Begin with rapport-building and context setting
- Use the "5 Whys" technique to drill down to root needs
- Ask for specific examples and recent experiences
- Explore both happy paths and pain points/error conditions
- Use props or prototypes to stimulate discussion
- Listen more than talk—aim for 80% listening, 20% talking
- Follow interesting threads but gently guide back to objectives
- Confirm understanding by summarizing and asking for validation

**Question Types**:
- **Open-ended**: "Walk me through how you currently perform X task"
- **Critical incident**: "Tell me about a time when something went wrong with Y"
- **Wish list**: "If you could change one thing about Z, what would it be?"
- **Comparison**: "How do you wish this process was different from current/other systems?"
- **Projection**: "How do you anticipate your needs for A changing in the next year?"
- **Process exploration**: "What happens before, during, and after you perform B?"
- **Exception handling**: "What do you do when C occurs (error, unexpected situation, etc.)?"

**Post-Interview**:
- Review and organize notes promptly while fresh
- Identify potential functional requirements from responses
- Look for patterns, contradictions, and gaps
- Prepare summary for participant validation
- Follow up on action items or open questions

### Workshops and Collaborative Sessions
Structured group activities to elicit and refine requirements.

**Types of Workshops**:
- **Requirements Elicitation Workshops**: Focused on discovering needs
- **User Story Mapping**: Creating physical/digital maps of user journeys
- **Impact Mapping**: Linking features to business goals and user behaviors
- **Event Storming**: Exploring system events and their consequences
- **Prioritization Workshops**: Using techniques like $100 voting or MoSCoW
- **Requirements Refinement**: Clarifying and detailing existing requirements

**Facilitation Best Practices**:
- Set clear objectives and agenda in advance
- Establish ground rules for participation and respect
- Ensure all voices are heard (use techniques like round-robin, silent writing)
- Use visual artifacts (sticky notes, whiteboards, index cards)
- Timebox activities to maintain energy and focus
- Capture outcomes visibly and comprehensively
- Schedule breaks to prevent fatigue
- Follow up with distributed summary and action items
- Consider using professional facilitator for complex or contentious topics

**Specific Techniques**:
- **Brainstorming**: Quantity-focused idea generation without judgment
- **Brainwriting**: Silent idea generation then sharing (reduces anchoring)
- **Affinity Mapping**: Grouping similar ideas to identify themes
- **Dot Voting**: Simple prioritization using stickers or marks
- **$100 Test**: Allocating budget across options to reveal preferences
- **Role Playing**: Acting out scenarios to uncover requirements
- **Prototype Walkthrough**: Reviewing mockups to elicit feedback
- **Backward Planning**: Starting from desired outcome and working backward

### Observation and Ethnography
Learning by watching users in their natural environment.

**Approaches**:
- **Naturalistic Observation**: Watching without interaction to minimize observer effect
- **Participant Observation**: Joining activities to gain deeper understanding
- **Shadowing**: Following users through their daily routines
- **Contextual Inquiry**: Interviewing while observing work in context
- **Think-Aloud Protocol**: Asking users to verbalize thoughts while performing tasks
- **Video Ethnography**: Recording for later analysis (with consent)

**What to Look For**:
- Actual vs. reported behavior (the "say-do" gap)
- Workarounds and informal practices
- Environmental factors affecting performance (noise, interruptions, etc.)
- Task sequences, frequency, and duration
- Tools and artifacts used alongside the system
- Communication patterns and handoffs
- Pain points, frustrations, and coping strategies
- Moments of delight or satisfaction
- Physical movements and ergonomic considerations
- Cognitive load and decision points
- Social interactions and collaborations

**Best Practices**:
- Obtain informed consent and explain purpose clearly
- Blend in as much as possible to reduce disruption
- Focus on goals and tasks rather than specific interface details
- Observe both experts and novices to see different approaches
- Notice what users avoid or struggle with as much as what they do
- Document observations promptly with timestamps and context
- Look for patterns across multiple observations
- Respect privacy and confidentiality of observed activities
- Consider multiple sessions at different times and days

### Prototyping and Modeling
Using preliminary versions to explore and validate requirements.

**Types of Prototypes**:
- **Paper Prototypes**: Hand-drawn sketches or printouts for early feedback
- **Wireframes**: Low-fidelity digital layouts showing structure and layout
- **Mockups**: Medium-fidelity representations with basic styling
- **Clickable Prototypes**: Interactive simulations showing flow and navigation
- **Functional Prototypes**: Working implementations of limited functionality
- **Horizontal Prototypes**: Broad coverage of features with shallow depth
- **Vertical Prototypes**: Deep implementation of narrow feature set

**When to Use Which**:
- **Early Exploration**: Paper sketches, whiteboard sessions, storyboards
- **Concept Validation**: Clickable prototypes, wireframes with basic interactivity
- **Usability Testing**: Interactive mockups representing key user journeys
- **Technical Feasibility**: Spike solutions proving specific architectures
- **Stakeholder Engagement**: Polished mockups showing vision and direction
- **Requirement Clarification**: Focused prototypes on ambiguous or complex areas

**Best Practices**:
- Clearly communicate prototype purpose and fidelity level
- Focus on learning objectives rather than polishing
- Use appropriate fidelity for the questions you're trying to answer
- Capture both quantitative data (task completion, time) and qualitative feedback
- Test with representative users in realistic contexts when possible
- Iterate rapidly based on feedback—don't get attached to early versions
- Document what was learned and how it changed understanding
- Plan for disposal or evolution of prototype based on approach chosen

### Document and Artifact Analysis
Extracting requirements from existing materials.

**Sources to Examine**:
- **Current System Documentation**: User manuals, help files, SOPs, training materials
- **Legacy System Code**: Especially when documentation is poor or missing
- **Policy and Procedure Documents**: Organizational rules that system must enforce
- **Regulatory Documents**: Laws, standards, and compliance requirements
- **Industry Best Practices**: Accepted methodologies and guidelines
- **Competitor Materials**: Marketing, feature lists, user guides, reviews
- **Customer Feedback**: Support tickets, complaint logs, satisfaction surveys
- **Business Plans**: Strategic documents outlining goals and objectives
- **Help Desk Logs**: Common problems and user difficulties
- **System Logs and Analytics**: Usage patterns, error rates, performance metrics
- **Forms and Templates**: Current paper or electronic forms used in processes
- **Reports and Dashboards**: Current outputs that system must replicate or improve
- **Integration Specifications**: Existing interfaces with other systems
- **Training Materials**: What users are currently taught to do

**Analysis Techniques**:
- **Keyword Extraction**: Identifying domain-specific terms and concepts
- **Process Mapping**: Creating flowcharts from documented procedures
- **Gap Analysis**: Comparing current state to desired future state
- **Cross-Referencing**: Linking related information across documents
- **Version Comparison**: Identifying changes and evolution over time
- **Stakeholder Annotation**: Having domain experts review and mark up documents
- **Use Case Derivation**: Identifying user goals from process descriptions
- **Data Flow Tracing**: Following information through documented processes
- **Decision Point Identification**: Finding where choices are made in procedures
- **Exception Handling Review**: Examining how errors and exceptions are currently managed

**Best Practices**:
- Focus on extracting needs and goals, not just copying existing solutions
- Look for pain points and inefficiencies in current processes
- Identify what works well that should be preserved
- Distinguish between prescriptive requirements and descriptive documentation
- Note inconsistencies between different documents as potential issues
- Consider the context and audience for each document
- Validate extracted requirements with subject matter experts
- Track source of each requirement for traceability and credibility

## 5. Common Mistakes in Writing Functional Requirements

### Vague or Ambiguous Language
**Mistake**: Using imprecise terms that lead to different interpretations
**Examples**:
- "The system should be user-friendly"
- "The system needs to handle lots of users quickly"
- "The system ought to be reliable and secure"
- "The system must provide adequate response times"

**Solutions**:
- Replace vague adjectives with measurable criteria
- Define terms like "user-friendly" in a glossary with specific metrics
- Specify exact quantities: "support 1,000 concurrent users"
- Replace "lots of" with specific numbers or ranges
- Use "shall" statements with clear, testable conditions
- Reference external standards or benchmarks where applicable
- Ask: "How will we objectively measure that this requirement is met?"

### Over-Specification of Solutions
**Mistake**: Dictating how instead of what, constraining design unnecessarily
**Examples**:
- "The system shall use Oracle Database 19c for all data storage"
- "The system shall implement authentication using LDAP over SSL"
- "The system shall display search results in a table with exactly 5 columns"
- "The system shall use Java Spring Boot version 2.5.4 for the backend"

**Solutions**:
- Focus on outcomes and goals rather than implementation details
- Specify what needs to be achieved, not how to achieve it
- Delay technical decisions until design phase when more information available
- Use interface requirements: "The system shall provide a RESTful API for data access"
- State performance or quality requirements instead of specific technologies
- Involve architects and developers to review for premature design decisions
- Consider creating separate "design constraints" document for necessary technical limitations
- Use phrases like: "The system shall support [capability] allowing implementation teams to choose appropriate technology"

### Under-Specification
**Mistake**: Lacking sufficient detail for design, implementation, or testing
**Examples**:
- "The system shall process customer orders"
- "The system shall allow users to search for products"
- "The system shall handle errors gracefully"
- "The system shall provide reporting capabilities"

**Solutions**:
- Add specificity: Who, what, when, where, how much, how often
- Define acceptance criteria that specify exact behavior under various conditions
- Break down complex requirements into smaller, more specific ones
- Use examples and scenarios to illustrate expected behavior
- Specify data formats, units, ranges, and precision where relevant
- Consider different user types, contexts, and usage patterns
- Address error handling and exception cases explicitly
- Ask: "If a developer read this requirement, would they know exactly what to build?"

### missing Actor or Beneficiary
**Mistake**: Not specifying who initiates or benefits from the function
**Examples**:
- "The system shall calculate tax"
- "The system shall send notifications"
- "The system shall generate reports"

**Solutions**:
- Identify the actor: "The system shall allow customers to calculate estimated tax"
- Specify the beneficiary: "The system shall send low inventory notifications to warehouse managers"
- Clarify initiation: "The system shall generate monthly sales reports upon request by sales managers"
- Consider multiple actors: "The system shall allow both customers and agents to initiate returns"
- For system-to-system interactions: "The system shall transmit order data to the fulfillment API"
- Ask: "Who performs this action? Who benefits from or needs this capability?"

### Conflicting Requirements
**Mistake**: Two or more requirements that cannot both be satisfied simultaneously
**Examples**:
- REQ-001: "The system shall allow unlimited file uploads"
- REQ-002: "The system shall limit storage usage to 2GB per user"
- REQ-003: "The system shall display real-time inventory levels"
- REQ-004: "The system shall update inventory only once per day to reduce processing load"

**Solutions**:
- Conduct consistency checking during requirements analysis
- Use techniques like pairwise comparison or dependency mapping
- Look for implicit assumptions that create conflicts when made explicit
- Facilitate stakeholder discussions to resolve conflicts objectively
- Look for compromise solutions that partially satisfy both
- Document trade-off decisions with clear rationale
- Consider temporal or contextual separation ("during peak hours...", "for premium users...")
- Escalate to appropriate decision-makers when necessary
- Implement change impact analysis to detect conflicts early

### Ignoring Non-Functional Aspects
**Mistake**: Writing functional requirements that implicitly assume non-functional qualities without stating them
**Examples**:
- "The system shall search product catalog" (without performance requirements)
- "The system shall process financial transactions" (without accuracy or security requirements)
- "The system shall display medical images" (without resolution or timing requirements)
- "The system shall allow concurrent editing" (without conflict resolution specifications)

**Solutions**:
- Identify implicit non-functional assumptions during requirements review
- Explicitly state performance, security, usability, and other quality requirements
- Consider non-functional aspects early in the elicitation process
- Use techniques like "non-functional requirements brainstorming" sessions
- Create traceability links between functional and non-functional requirements
- Ask: "What happens if this function is slow/unreliable/insecure/difficult to use?"
- Consider creating combined requirements that specify both function and quality

### Poor Organisation and Structure
**Mistake**: Requirements that are difficult to navigate, understand, or maintain
**Examples**:
- Hundreds of requirements in a single flat list without grouping
- Inconsistent formatting and structure across requirements
- Missing or unclear identifiers making traceability difficult
- Requirements scattered across multiple documents without cross-references
- No clear hierarchy or organization scheme

**Solutions**:
- Group requirements by feature, module, user role, or business process
- Use consistent numbering or identification scheme (e.g., FR-001, FR-002)
- Establish and follow a standard requirements template
- Create table of contents, index, and searchable format
- Use hierarchical organization (chapters, sections, subsections)
- Implement requirements management tool with proper structuring capabilities
- Establish naming conventions for consistency
- Regularly clean up and reorganize as understanding evolves
- Consider different views for different stakeholders (technical vs business)

### Lack of Validation
**Mistake**: Writing requirements in isolation without checking with stakeholders
**Examples**:
- Requirements written solely by developers based on assumptions
- Requirements based on outdated information or stereotypes
- Requirements that reflect what's easy to build rather than what's needed
- Requirements that miss critical user workflows or pain points
- Requirements that include unnecessary "nice-to-haves" while missing essentials

**Solutions**:
- Implement regular requirements review cycles with stakeholders
- Use techniques like requirements walkthroughs and inspections
- Create prototypes or models to validate understanding
- Apply the "so what?" test: If this requirement weren't met, what would be the impact?
- Validate with representative users, not just proxies or intermediaries
- Consider different validation techniques for different requirement types
- Document validation results and incorporate feedback
- Establish definition of done that includes stakeholder validation
- Plan for ongoing validation throughout development, not just upfront

### Inappropriate Level of Detail
**Mistake**: Requirements that are either too vague for implementation or too detailed for current stage
**Examples**:
- Too early: Specifying exact database schemas and API endpoints during concept phase
- Too late: Leaving critical business rules undefined during detailed design
- Inconsistent: Some requirements at high level, others at excessive detail

**Solutions**:
- Match level of detail to stage of development and available knowledge
- Use progressive elaboration: Start high-level, add detail as understanding increases
- Consider different requirement types for different purposes (vision vs specification)
- Use techniques like "just-in-time detailing" for agile approaches
- Establish guidelines for appropriate detail at different phases
- Involve implementers to provide feedback on whether requirements are actionable
- Use product backlog grooming in agile to refine items before development
- Consider creating multiple requirement documents for different audiences and purposes

## 6. Practical Exercise: Writing Functional Requirements

### Scenario
You are creating requirements for an online banking system that will allow customers to manage their accounts, transfer funds, pay bills, and deposit checks via mobile device.

### Exercise Part 1: Identifying Functional Requirements from User Goals
Convert these user goals into specific functional requirements using the "shall" statement format.

**User Goals**:
1. Customers want to check their account balances quickly and securely
2. Customers want to transfer money between their own accounts
3. Customers want to send money to friends and family
4. Customers want to pay their bills electronically
5. Customers want to deposit checks using their phone's camera
6. Customers want to view their transaction history
7. Customers want to receive alerts for account activity
8. Customers want to locate nearby ATMs and branches

**Sample Answers**:
1. "The system shall allow authenticated users to view current balances for all linked accounts"
2. "The system shall allow authenticated users to transfer funds between their own accounts"
3. "The system shall allow authenticated users to send money to other individuals using email or phone number"
4. "The system shall allow authenticated users to schedule and execute electronic bill payments"
5. "The system shall allow authenticated users to deposit checks by capturing images of front and back of check"
6. "The system shall allow authenticated users to view transaction history with filtering and search capabilities"
7. "The system shall allow authenticated users to configure and receive alerts for specified account events"
8. "The system shall use device location services to display nearby ATMs and branches on a map"

### Exercise Part 2: Writing User Stories with Acceptance Criteria
Write user stories in the standard format for three of the user goals above, including acceptance criteria in Given/When/Then format.

**Sample Answers**:
- **Story**: As a bank customer, I want to view my account balances so I can monitor my financial status
  - **Given**: Authenticated user on account summary page
  - **When**: User navigates to account balance section
  - **Then**: System displays current and available balances for each linked account
  - **And**: Balances are updated to reflect all posted transactions
  - **And**: System indicates when balances were last updated
  - **Given**: User viewing account balances
  - **When**: User selects a specific account
  - **Then**: System displays detailed balance information including pending transactions
  - **And**: System shows balance trends over configurable time periods
  - **Given**: User has just completed a transaction
  - **When**: User refreshes or navigates away and back to account summary
  - **Then**: System displays updated balances reflecting the recent transaction
  - **And**: System indicates the effective date/time of the balance update

- **Story**: As a bank customer, I want to deposit a check using my phone's camera so I don't need to visit a branch or ATM
  - **Given**: Authenticated user on check deposit screen with proper lighting and steady hand
  - **When**: User captures clear images of front and back of endorsed check
  - **Then**: System validates images meet quality requirements (sufficient light, full check visible, etc.)
  - **And**: System extracts check details (amount, payee, account numbers) using OCR and MICR reading
  - **And**: System displays extracted information for user confirmation
  - **And**: User confirms or corrects extracted information
  - **And**: System processes check deposit and provides confirmation with estimated availability date
  - **And**: System transmits deposit information to banking backend for clearing
  - **Given**: User attempts to deposit check with poor image quality
  - **When**: System analyzes captured images
  - **Then**: System provides specific feedback on what needs improvement (blur, lighting, cropping, etc.)
  - **And**: System allows user to retake images without restarting process
  - **Given**: User attempts to deposit check already deposited (duplicate detection)
  - **When**: System processes check images
  - **Then**: System detects potential duplicate based on check attributes
  - **And**: System prompts user to confirm this is a new deposit
  - **And**: If confirmed as duplicate, system rejects deposit and advises user to retain or destroy check appropriately
  - **Given**: User wants to deposit check for account in different currency
  - **When**: User initiates check deposit and selects target account
  - **Then": System validates check currency matches account currency
  - **And: If mismatch, system displays error and prevents deposit
  - **And: System suggests alternative methods for foreign currency checks (branch deposit, etc.)

- **Story**: As a bank customer, I want to transfer money to friends and family so I can conveniently share expenses or send gifts
  - **Given**: Authenticated user logged into banking app
  - **When**: User selects "Transfer to Another Person" option
  - **Then**: System presents options to send via email, phone number, or existing contact
  - **And**: System displays daily and per-transaction limits for transfers
  - **Given**: User has selected recipient and entered amount
  - **When**: User reviews transfer details and confirms transaction
  - **Then**: System validates sufficient funds in source account
  - **And**: System verifies recipient contact information is verification status (if applicable)
  - **And**: System creates pending transfer record with unique identifier
  - **And**: System sends notification to recipient with instructions to claim funds
  - **And**: System deducts transfer amount from source account immediately (or places on hold)
  - **And**: System provides user with confirmation and estimated delivery time
  - **Given**: User attempts to transfer amount exceeding daily limit
  - **When**: User enters amount and attempts to confirm transfer
  - **Then**: System displays error message showing limit and amount entered
  - **And**: System prevents transaction completion until amount is reduced below limit
  - **And**: System allows user to adjust amount and retry
  - **Given": User sends transfer to unregistered recipient
  - **When": Recipient attempts to claim funds using provided link
  - **Then: System verifies sender's identity and transaction details
  - **And: System prompts recipient to provide information needed to register for service
  - **And: Upon successful registration, system transfers funds to recipient's designated account
  - **And: System notifies both sender and recipient when funds have been successfully transferred

### Exercise Part 3: Creating Use Case Scenarios
Create a use case for one of the banking features, including main flow and at least three extensions.

**Sample Answer: Use Case - Transfer Funds Between Own Accounts**
- **Name**: Transfer Funds Between Customer's Own Accounts
- **Primary Actor**: Customer
- **Secondary Actors**: None (all processing within system)
- **Stakeholders and Interests**:
  - Customer: Wants quick, easy way to move money between their accounts
  - Bank: Reduces branch teller workload for simple transfers
  - Accounting: Requires accurate tracking of internal fund movements
- **Preconditions**: Customer authenticated, has at least two accounts with sufficient funds in source account
- **Main Flow**:
  1. Customer selects "Transfer Between My Accounts" option
  2. System displays list of customer's accounts with current balances
  3. Customer selects source account from which to transfer funds
  4. System validates selected account has sufficient funds for transfer
  5. Customer selects destination account to receive funds
  6. Customer enters transfer amount
  7. System validates amount is numeric, positive, and within account limits
  8. System displays transfer summary showing source, destination, amount, and fees (if any)
  9. Customer confirms transfer details
  10. System debits amount from source account
  11. System credits amount to destination account
  12. System updates account balances and transaction histories for both accounts
  13. System generates transfer confirmation with timestamp and reference number
  14. System displays confirmation screen to customer
  15. System sends optional notification (email/SMS) if customer has enabled transfer alerts
- **Extensions**:
  3a. Customer has only one account: Display message "You need at least two accounts to perform this action" and suggest alternatives (external transfer, etc.)
  4a. Source account has insufficient funds: Display specific shortage amount and options: "Cancel," "Reduce amount," or "Add funds from external source"
  7a. Transfer amount exceeds daily limit: Display limit error and maximum allowable amount, prevent confirmation until amount reduced
  8a. Customer modifies transfer details: Allow editing of amount, source, or destination with re-validation
  10a. Insufficient funds during debit (race condition): Credit any partially debited amount, display error, suggest retry
  11a. System failure during credit: Debit amount already deducted from source, display error with instructions to contact support
  12a. Database update failure: Rollback both debit and credit operations, display error, log incident for investigation
  14a. Customer declines to send notification: Skip notification step but still complete transfer
  15a. Notification service failure: Log error but do not fail the transfer (non-blocking dependency)
- **Postconditions**: Source account decreased by transfer amount, destination account increased by same amount, transaction recorded in both accounts' histories, confirmation provided to customer
- **Trigger**: Customer initiates transfer between own accounts
- **Frequency**: Approximately 15 transfers per active customer per month
- **Priority**: Must have for initial release
- **Non-Functional Requirements**:
  - Performance: Complete transfer within 5 seconds 95% of time
  - Security: Require re-authentication for transfers over $10,000
  - Auditability: Complete audit trail for all transfers including timestamps and operator IDs
  - Availability: 99.9% uptime for transfer function
  - Accuracy: Zero tolerance for incorrect amounts or account attributions

### Exercise Part 4: Identifying Missing or Implicit Requirements
Review this set of functional requirements for a prescription refill feature and identify what's missing or implied but not stated.

**Given Requirements**:
- "The system shall allow patients to request prescription refills"
- "The system shall notify patients when their refill is ready for pickup"
- "The system shall update prescription status when refilled"
- "The system shall allow patients to view their prescription history"

**Missing/Implied Requirements**:
- **Authentication/Authorization**: 
  - "The system shall require patient authentication before allowing prescription refill requests"
  - "The system shall ensure patients can only request refills for their own prescriptions"
  - "The system shall validate patient identity using secure authentication methods"
  
- **Prescription Validation**:
  - "The system shall verify prescription has refills remaining before allowing refill request"
  - "The system shall check prescription expiration date and reject requests for expired prescriptions"
  - "The system shall verify prescribing physician is still active and authorized to prescribe"
  - "The system shall check for drug interactions or contraindications based on patient's other medications"
  
- **Refill Processing Details**:
  - "The system shall allow patients to select preferred pharmacy location for pickup"
  - "The system shall transmit refill request to selected pharmacy for processing"
  - "The system shall provide estimated time for refill processing based on pharmacy workload"
  - "The system shall allow patients to specify quantity if different from original prescription"
  - "The system shall validate requested quantity does not exceed prescribed amount or refill limits"
  
- **Notification Specifics**:
  - "The system shall send refill ready notification via patient's preferred method (SMS, email, app push)"
  - "The system shall include pickup location, prescription name, and expiration date in notification"
  - "The system shall allow patients to configure when they want to be notified (same day, day before, etc.)"
  - "The system shall resend notification if not acknowledged within specified time period"
  
- **Status Updates**:
  - "The system shall track and display prescription status through all stages: requested, processing, ready for pickup, picked up, expired"
  - "The system shall allow pharmacy staff to update status as prescription moves through fulfillment process"
  - "The system shall notify prescribing physician when refill is dispensed (if required by regulations)"
  - "The system shall flag prescriptions that have not been picked up within specified time for follow-up"
  
- **History and Tracking**:
  - "The system shall show original prescription date, prescribing physician, and prescribed quantity in history"
  - "The system shall display fill dates, quantities, and pharmacy location for each refill in history"
  - "The system shall allow patients to export prescription history for insurance or tax purposes"
  - "The system shall retain prescription history for minimum period required by regulations (typically 2-7 years)"
  
- **Error Handling and Exceptions**:
  - "The system shall handle cases where prescription is no longer active or has been discontinued"
  - "The system shall provide clear guidance when refill is rejected due to insurance restrictions"
  - "The system shall allow patients to request new prescription when refills are exhausted"
  - "The system shall handle situations where patient attempts to refill controlled substance too early"
  - "The system shall comply with regional regulations regarding prescription refills (vary by state/jurisdiction)"
  
- **Usability and Accessibility**:
  - "The system shall preserve patient privacy by not displaying full prescription details in notifications"
  - "The system shall support accessibility features for patients with visual or motor impairments"
  - "The system shall work across different devices (smartphone, tablet, computer)"
  - "The system shall provide alternative refill methods for patients without smartphone access (phone IVR, website)"
  - "The system shall minimize number of steps required to request refill (aim for 3 taps or less)"
  
- **Business Rules and Constraints**:
  - "The system shall enforce maximum refill quantity based on prescription and insurance limits"
  - "The system shall prevent refill requests for medications that require prior authorization every time"
  - "The system shall allow healthcare providers to set refill limitations on prescriptions"
  - "The system shall handle split filling when pharmacy cannot dispense full quantity at once"
  - "The system shall notify patients of any changes to prescription made by healthcare provider"

## 7. Checklist for Evaluating Functional Requirements

Use this checklist to assess whether your functional requirements meet quality standards:

### Basic Structure and Format
- [ ] Each requirement has a unique, persistent identifier
- [ ] Requirement uses correct mandatory language ("shall" for requirements)
- [ ] Requirement is formatted consistently with other requirements
- [ ] Requirement includes clear identification of who/what performs the action
- [ ] Requirement specifies what object or data the action is performed on
- [ ] Requirement includes necessary conditions, constraints, or qualifiers
- [ ] Requirement avoids design or solution specification unless absolutely necessary
- [ ] Requirement is written in present tense, not future tense
- [ ] Requirement is free of spelling, grammar, and punctuation errors
- [ ] Requirement avoids marketing language, hype, or subjective statements
- [ ] Requirement focuses on need, not wish_list or nice_to_have

### Content and Clarity
- [ ] Requirement expresses a single, coherent idea or function
- [ ] Requirement is understandable to intended audience (technical vs business)
- [ ] Requirement does not contain ambiguous or vague terms
- [ ] All acronyms, abbreviations, and specialized terms are defined
- [ ] Requirement specifies measurable outcomes where applicable
- [ ] Requirement includes necessary preconditions and assumptions
- [ ] Requirement addresses both normal operation and relevant error conditions
- [ ] Requirement is feasible to implement with available resources and technology
- [ ] Requirement is necessary to meeting stakeholder needs or business objectives
- [ ] Requirement does not duplicate or overlap unnecessarily with other requirements

### Completeness and Specificity
- [ ] Requirement specifies who initiates or performs the action (actor, role, or system)
- [ ] Requirement specifies what data, objects, or systems are acted upon
- [ ] Requirement specifies when or under what conditions the action occurs
- [ ] Requirement specifies how the action is performed (when necessary for clarity)
- [ ] Requirement specifies what happens as a result of the action
- [ ] Requirement specifies acceptable ranges, limits, or thresholds where applicable
- [ ] Requirement specifies data formats, units, precision, and formatting where relevant
- [ ] Requirement specifies sequencing or ordering requirements where relevant
- [ ] Requirement specifies handling of edge cases, boundaries, and exceptions
- [ ] Requirement specifies any necessary cleanup, rollback, or recovery actions
- [ ] Requirement specifies notification or confirmation requirements where appropriate

### Traceability and Alignment
- [ ] Requirement can be traced to a legitimate source (stakeholder interview, document, regulation, goal)
- [ ] Requirement supports forward traceability to design components or modules
- [ ] Requirement supports forward traceability to test cases or validation procedures
- [ ] Requirement aligns with stated business objectives or user needs
- [ ] Requirement does not contradict any other requirement in the set
- [ ] Requirement uses consistent terminology with glossary and other requirements
- [ ] Requirement is at appropriate level of detail for current phase of development
- [ ] Requirement does not prematurely specify implementation or design decisions
- [ ] Requirement includes rationale or justification where helpful for understanding
- [ ] Requirement indicates priority or importance level where relevant

### Testability and Validation
- [ ] Requirement includes clear, measurable acceptance criteria
- [ ] Acceptance criteria are objectively evaluable (not based on opinion or interpretation)
- [ ] Requirement can be validated through inspection, analysis, demonstration, or testing
- [ ] Test cases can be readily derived from acceptance criteria
- [ ] Acceptance criteria specify tools, methods, or standards to be used for evaluation
- [ ] Requirement specifies conditions under which it must be met (environment, load, etc.)
- [ ] Requirement distinguishes between mandatory behavior and optional features
- [ ] Acceptance criteria are feasible to validate within project constraints (time, budget, etc.)
- [ ] Requirement supports both positive testing (valid inputs) and negative testing (invalid inputs)
- [ ] Requirement specifies expected behavior for error conditions and exception handling
- [ ] Acceptance criteria specify timing or frequency requirements where applicable

### Professional Quality
- [ ] Requirement contributes to clear, organized requirements set
- [ ] Similar requirements are structured consistently for ease of comparison
- [ ] Requirement has been reviewed by relevant stakeholders for accuracy
- [ ] Requirement has been validated with end users where applicable
- [ ] Requirement has been examined for consistency with related requirements
- [ ] Requirement has been checked for feasibility with technical experts
- [ ] Requirement has been assessed for usability implications where relevant
- [ ] Requirement has been evaluated for security and privacy implications where relevant
- [ ] Requirement has been reviewed for regulatory and compliance implications where appropriate
- [ ] Requirement shows evidence of iterative refinement based on feedback
- [ ] Requirement is appropriate for inclusion in requirements baseline
- [ ] Requirement definition of done criteria have been met for this requirement

## 8. Definition of Done for Functional Requirements

Functional requirements for a specific increment, release, or iteration are considered complete when:

### Elicitation and Collection
- [ ] All relevant stakeholder groups have been consulted using appropriate methods
- [ ] New stakeholders discovered during the process have been identified and engaged
- [ ] Relevant documents, systems, and data sources have been examined for requirements
- [ ] Regulatory and compliance requirements have been identified and documented
- [ ] Non-functional requirements have been elicited where they impact or constrain functionality
- [ ] User goals, tasks, and scenarios have been explored to derive functional requirements
- [ ] Pain points, workarounds, and undesirable behaviors of current systems have been identified
- [ ] Desired outcomes and benefits have been clarified from stakeholder perspective
- [ ] Assumptions, constraints, and dependencies have been documented and validated
- [ ] Open questions and uncertainties have been recorded with owners and target resolution dates

### Analysis and Specification
- [ ] Requirements have been analyzed for completeness, consistency, and feasibility
- [ ] Conflicting requirements have been identified, discussed, and resolved with documented decisions
- [ ] Ambiguous, vague, or unclear requirements have been clarified with measurable precision
- [ ] Redundant or duplicative requirements have been identified and eliminated
- [ ] Requirements have been specified in appropriate format(s) for intended audiences
- [ ] Each requirement has a unique, persistent identifier that survives text changes
- [ ] Acceptance criteria have been defined for each requirement
- [ ] Requirements have been prioritized using agreed-upon method and criteria
- [ ] Glossary of domain-specific terms is complete and reviewed by subject matter experts
- [ ] Requirements are organized logically for easy navigation, reference, and understanding
- [ ] Diagrams, models, or visual representations have been created where beneficial
- [ ] Requirements have been allocated to appropriate components, subsystems, or services
- [ ] Data flow and interface requirements have been specified where relevant
- [ ] State transition and behavior requirements have been specified for stateful systems
- [ ] Error handling and exception requirements have been specified for all major functions
- [ ] Input validation and output requirements have been specified where relevant
- [ ] Timing, frequency, and sequencing requirements have been specified where needed
- [ ] Localization and internationalization requirements have been identified where applicable
- [ ] Accessibility and usability requirements have been considered for all user-facing functions
- [ ] Security and privacy requirements have been identified where functions handle sensitive data
- [ ] Performance and scalability requirements have been identified where relevant
- [ ] Maintenance and support requirements have been identified where applicable
- [ ] Requirements have been checked for feasibility with architects and developers
- [ ] Requirements have been assessed for testability and validation approaches
- [ ] Requirements have been reviewed for potential technical debt or maintenance issues
- [ ] Lessons learned from the requirements process have been documented for future improvement

### Validation and Agreement
- [ ] Requirements have been reviewed with stakeholders for accuracy and completeness
- [ ] Requirements have been validated with end users where applicable through multiple techniques
- [ ] Non-functional requirements have been validated with relevant experts (performance, security, etc.)
- [ ] Regulatory and compliance requirements have been validated with appropriate specialists
- [ ] Requirements have been assessed for clarity and understandability by intended audience
- [ ] Requirements baseline has been established, documented, and communicated
- [ ] Formal agreement or sign-off has been obtained from key stakeholder representatives
- [ ] Change control process has been defined, documented, and agreed upon
- [ ] Traceability links have been established between requirements and their sources
- [ ] Work has begun on establishing forward traceability to design concepts
- [ ] Testability of requirements has been assessed and confirmed as feasible
- [ ] Definition of done criteria have been met for the requirements set as a whole
- [ ] Plan exists for ongoing requirements refinement during development phases
- [ ] Stakeholders understand which requirements are in vs. out of current scope/release
- [ ] Estimates of effort, complexity, and risk have been assigned to requirements where appropriate
- [ ] Dependencies between requirements have been identified, documented, and managed
- [ ] Requirements have been reviewed for potential user experience and accessibility issues
- [ ] Requirements have been evaluated for alignment with architectural principles and constraints
- [ ] Requirements have been checked for legal and regulatory compliance where applicable
- [ ] Requirements have been assessed for potential security and privacy implications where handling sensitive data
- [ ] Requirements have been examined for performance characteristics and scalability implications
- [ ] Requirements have been reviewed for maintainability and technical debt considerations
- [ ] Requirements have been validated for consistency with organizational standards and policies
- [ ] Definition of done for each individual requirement has been met according to the checklist above

## 9. Related Topics

- [[01-REQUIREMENTS-OVERVIEW|01 — Requirements Overview]]: Foundational concepts about requirements engineering
- [[03-NON-FUNCTIONAL-REQUIREMENTS|03 — Non-Functional Requirements]]: Qualities and constraints that describe how well the system performs
- [[04-TECHNICAL-REQUIREMENTS|04 — Technical Requirements]]: Specific technology, architecture, and implementation constraints
- [[05-SECURITY-REQUIREMENTS|05 — Security Requirements]]: Protection mechanisms for data, systems, and users
- [[08-ARCHITECTURE|08 — Architecture]]: How functional requirements translate into system structure and design
- [[09-DESIGN|09 — Design]]: Detailed specification of how the system will fulfill functional requirements
- [[10-IMPLEMENTATION|10 — Implementation]]: Building the system to satisfy functional requirements
- [[11-TESTING|11 — Testing]]: Verifying that the system correctly implements functional requirements
- [[12-DEPLOYMENT|12 — Deployment]]: Releasing the system that implements functional requirements to users
- [[02-PROBLEM-DEFINITION|02 — Problem Definition]]: Understanding the problem space precedes defining solution requirements
- [[03-BUSINESS-UNDERSTANDING|03 — Business Understanding]]: Business goals and value context for functional requirements
- [[04-STAKEHOLDERS|04 — Stakeholders]]: Identifying who cares about which functional requirements
- [[05-USER-RESEARCH|05 — User Research]]: Direct insights from users that inform functional requirements
- [[06-USER-PERSONAS|06 — User Personas]]: Framing functional requirements from specific user perspectives
- [[07-REQUIREMENTS|07 — Requirements]]: The parent phase that encompasses all requirement types
- [[47-SENIOR-ENGINEERING-AND-RETROSPECTIVE|47 — SENIOR ENGINEERING AND RETROSPECTIVE]]: Lessons learned from functional requirements processes