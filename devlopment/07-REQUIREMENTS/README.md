# 07 — REQUIREMENTS

## 1. Purpose

The Requirements phase focuses on eliciting, analyzing, specifying, and validating the needs and constraints that a software system must satisfy. This phase bridges the gap between understanding the problem space (from previous phases) and defining what the solution should do. Effective requirements engineering ensures that the development team builds the right product that addresses genuine user needs and business objectives while managing stakeholder expectations and minimizing costly rework.

## 2. Activities

Key activities in the Requirements phase include:
- **Elicitation**: Gathering requirements from stakeholders through interviews, workshops, observation, and document analysis
- **Analysis**: Examining requirements for consistency, feasibility, and completeness; resolving conflicts
- **Specification**: Documenting requirements in clear, unambiguous formats (user stories, use cases, functional specifications)
- **Validation**: Confirming that requirements accurately reflect stakeholder needs and are achievable
- **Management**: Tracking changes, maintaining traceability, and prioritizing requirements throughout the project lifecycle
- **Prioritization**: Ranking requirements based on business value, risk, dependencies, and implementation effort
- **Traceability**: Establishing links between requirements, design elements, test cases, and business objectives

## 3. Outputs

Typical outputs from the Requirements phase include:
- **Requirements Document**: Comprehensive specification of functional and non-functional requirements
- **User Stories/Use Cases**: Descriptions of system behavior from user perspectives
- **Acceptance Criteria**: Clear conditions that must be met for requirements to be considered satisfied
- **Requirements Traceability Matrix**: Links between requirements and other project artifacts
- **Prioritized Backlog**: Ordered list of features or user stories for development
- **Glossary**: Definitions of domain-specific terms used in requirements
- **Stakeholder Map**: Identification of who cares about which requirements
- **Assumptions and Constraints Document**: Record of factors limiting solution options
- **Open Issues Log**: Unresolved questions or disagreements needing attention

## 4. Workflow

The Requirements phase typically follows this workflow:
1. **Planning**: Define requirements process, identify stakeholders, gather background information
2. **Elicitation**: Conduct interviews, workshops, surveys, and observation to collect raw requirements
3. **Analysis**: Organize, clarify, and prioritize gathered information; identify conflicts and gaps
4. **Specification**: Document requirements in appropriate formats for different audiences
5. **Validation**: Review requirements with stakeholders to confirm accuracy and completeness
6. **Management**: Establish baselines, track changes, and maintain requirements throughout development
7. **Sign-off**: Obtain formal agreement on requirements baseline before proceeding to design

## 5. Real-World Example

**Context**: A healthcare startup developing a patient portal for appointment scheduling and medical record access.

**Requirements Process**:
1. **Stakeholder Identification**: Patients, doctors, nurses, admin staff, insurance providers, IT support
2. **Elicitation**: 
   - Patients: Interviews revealed desire for 24/7 booking, prescription renewals, and test result access
   - Doctors: Workshops showed need for schedule management and patient communication tools
   - Admin: Observation highlighted pain points in manual scheduling and insurance verification
3. **Analysis**: 
   - Conflicting requirements: Patients wanted instant booking; doctors needed buffer times between appointments
   - Resolution: Implemented smart scheduling with configurable buffers and patient waitlists
   - Regulatory discovery: HIPAA compliance requirements emerged as critical constraints
4. **Specification**: 
   - User stories: "As a patient, I want to book appointments online so I don't need to call during business hours"
   - Use cases: Detailed flows for appointment scheduling, cancellation, and rescheduling
   - Non-functional: Security requirements for PHI protection, performance targets for page load times
5. **Validation**: 
   - Prototypes tested with patient focus groups revealed confusion about insurance terminology
   - Revised language to use plain terms instead of jargon
   - Security team validated encryption and access control implementations
6. **Management**: 
   - Changes tracked via Jira with requirement IDs linked to test cases
   - Weekly backlog grooming sessions adjusted priorities based on user feedback
   - Traceability matrix ensured all requirements had corresponding tests

**Outcome**: The portal launched with 80% patient adoption in first month, reducing phone call volume by 40% and improving appointment show rates through automated reminders.

## 6. Junior vs Senior Perspectives

### Junior Developer View
- Focuses on writing down what users say they want
- May treat all requirements as equally important
- Tends to specify technical solutions too early ("we should use React for this")
- Often misses implicit requirements (security, performance, usability)
- Might document requirements without validating understanding
- Struggles with prioritization when everything seems important
- May create overly technical specifications that business stakeholders can't understand

### Senior Developer View
- Distinguishes between stated needs and underlying goals
- Uses techniques like "5 Whys" to root-cause analysis
- Balances user desires with technical feasibility and business constraints
- Identifies and documents non-functional requirements early
- Creates requirements that are testable and unambiguous
- Establishes clear prioritization frameworks (MoSCoW, WSJF, etc.)
- Ensures requirements are understandable to both technical and non-technical audiences
- Plans for requirement evolution and manages expectations about change
- Recognizes that incomplete or changing requirements are normal and builds processes to handle them

## 7. Common Mistakes

- **Ambiguous Language**: Using words like "should", "could", "may", "fast", "user-friendly" without measurable criteria
- **Missing Non-Functional Requirements**: Forgetting performance, security, scalability, or usability constraints until late in development
- **Over-Specification**: Dictating technical solutions (e.g., "use Oracle database") instead of stating needs
- **Under-Specification**: Being too vague ("system shall be reliable") leading to differing interpretations
- **Ignoring Stakeholders**: Failing to consult all relevant parties, leading to overlooked needs or resistance
- **No Prioritization**: Treating all requirements as must-haves, causing scope creep and missed deadlines
- **Lack of Traceability**: Unable to trace why a feature exists or what tests cover it
- **Not Validating**: Writing requirements in isolation without checking with actual users
- **Overlooking Assumptions**: Not documenting context-dependent requirements that may change
- **Poor Organization**: Creating requirements documents that are hard to navigate or maintain
- **Confusing Requirements with Design**: Specifying how instead of what
- **Neglecting Acceptance Criteria**: Making it impossible to determine when a requirement is done
- **Ignoring Dependencies**: Not recognizing that some requirements must be implemented before others
- **Failure to Update**: Letting requirements become outdated as understanding evolves
- **Too Much Detail Early**: Over-specifying before sufficient knowledge is available
- **Not Considering Edge Cases**: Focusing only on happy paths and missing error conditions
- **Ignoring Regulatory Requirements**: Overlooking compliance needs that can derail projects late
- **Assuming Consensus**: Mistaking silence for agreement in requirements workshops
- **Not Managing Expectations**: Failing to communicate that not all requested features will be in initial release
- **Overlooking Integration Needs**: Not specifying how the system will work with existing tools
- **Neglecting Migration Requirements**: Forgetting to plan for data migration from legacy systems

## 8. Risks

- **Building the Wrong Product**: Requirements that don't address real user needs lead to low adoption
- **Scope Creep**: Uncontrolled growth of requirements extends timelines and budgets
- **Requirements Volatility**: Frequent changes disrupt planning and cause rework
- **Stakeholder Dissatisfaction**: Misaligned expectations lead to conflict and project resistance
- **Technical Impossibility**: Requirements that can't be fulfilled with available technology or skills
- **Regulatory Non-Compliance**: Missing legal requirements results in fines or inability to launch
- **Performance Failures**: Systems that don't meet speed, scale, or responsiveness needs
- **Security Vulnerabilities**: Overlooked security requirements create exploitable weaknesses
- **Usability Issues**: Systems that are technically correct but difficult or frustrating to use
- **Integration Problems**: Incompatibility with existing systems increases complexity and cost
- **Maintenance Nightmares**: Poor requirements make future changes risky and expensive
- **Team Miscommunication**: Different interpretations of requirements lead to inconsistent implementation
- **Testing Gaps**: Untestable requirements result in undiscovered defects
- **Budget Overruns**: Underestimated effort due to unclear or changing requirements
- **Schedule Delays**: Repeated requirement revisions push out timelines
- **Loss of Trust**: Stakeholders lose confidence when requirements keep changing
- **Missed Business Value**: Failure to capture most important features reduces ROI
- **Legal Liability**: Inadequate requirements for safety-critical systems can lead to harm
- **Vendor Lock-in**: Overly specific requirements limit future flexibility
- **Knowledge Loss**: Poor documentation makes it hard for new team members to understand why things are built certain ways
- **Competitive Disadvantage**: Slow response to market changes due to rigid requirements processes

## 9. Checklist

- [ ] All key stakeholders have been identified and consulted
- [ ] Requirements are documented in clear, unambiguous language
- [ ] Each requirement has a unique identifier for traceability
- [ ] Functional requirements describe what the system should do
- [ ] Non-functional requirements cover performance, security, usability, etc.
- [ ] Requirements are traceable to business objectives or user needs
- [ ] Conflicting requirements have been identified and resolved
- [ ] Assumptions and constraints are explicitly documented
- [ ] Acceptance criteria are defined for each requirement
- [ ] Requirements have been validated with stakeholders
- [ ] Prioritization scheme is established and agreed upon
- [ ] Requirements are at appropriate level of detail for current phase
- [ ] No design decisions are prematurely embedded in requirements
- [ ] Requirements are organized for easy navigation and reference
- [ ] Glossary defines domain-specific terminology
- [ ] Requirements documents are version-controlled
- [ ] Process exists for managing changes to requirements
- [ ] Traceability links exist between requirements and tests
- [ ] Regulatory and compliance requirements have been identified
- [ ] Performance requirements include measurable metrics
- [ ] Security requirements address authentication, authorization, data protection
- [ ] Usability requirements consider user skills, disabilities, and contexts
- [ ] Requirements have been reviewed for feasibility
- [ ] Open issues and questions are documented with owners
- [ ] Requirements baseline has been established and agreed upon
- [ ] Plan exists for requirements validation during development
- [ ] Stakeholders understand which requirements are in vs. out of scope for current release
- [ ] Requirements consider future extensibility and modification needs
- [ ] Non-functional requirements have been allocated to specific components where appropriate
- [ ] Requirements documentation avoids marketing language and focuses on facts

## 10. Definition of Done

The Requirements phase is considered complete when:
- All key stakeholder groups have been consulted and their needs documented
- Functional requirements are written as clear, testable statements
- Non-functional requirements (performance, security, usability, etc.) are specified with measurable criteria
- Requirements have been validated with stakeholders through formal review sessions
- Conflicting requirements have been identified, discussed, and resolved with documented decisions
- Each requirement has unambiguous acceptance criteria
- Requirements are traceable to business objectives, user goals, or stakeholder needs
- Assumptions, constraints, and dependencies are explicitly documented
- A prioritized requirements backlog exists with clear ranking criteria
- Requirements are organized in a navigable format with table of contents, index, and searchability
- Glossary of domain terms is complete and reviewed by subject matter experts
- Open issues log documents unresolved questions with owners and target resolution dates
- Requirements baseline has been established and agreed upon by key stakeholders
- Change control process is defined and agreed upon for managing requirement modifications
- Traceability matrix links requirements to future design elements and test cases
- Regulatory and compliance requirements have been identified and documented
- Performance requirements include specific, measurable targets (response times, throughput, etc.)
- Security requirements address authentication, authorization, encryption, and auditing needs
- Usability requirements consider target user skills, accessibility needs, and usage contexts
- Requirements have been assessed for technical feasibility and rough effort estimates
- Stakeholders have signed off on the requirements baseline for the current release scope
- Plan exists for ongoing requirements refinement during development phases
- Lessons learned from the requirements process have been captured for future improvement

## 11. Related Topics

- [[02-PROBLEM-DEFINITION|02 — Problem Definition]]: Understanding the problem space precedes defining solution requirements
- [[03-BUSINESS-UNDERSTANDING|03 — Business Understanding]]: Business goals and value inform requirements prioritization
- [[04-STAKEHOLDERS|04 — Stakeholders]]: Identifying and analyzing stakeholders is essential for requirements elicitation
- [[05-USER-RESEARCH|05 — User Research]]: Direct user insights feed into accurate requirements gathering
- [[06-USER-PERSONAS|06 — User Personas]]: Personas help frame requirements from specific user perspectives
- [[08-ARCHITECTURE|08 — Architecture]]: Requirements drive architectural decisions and must be achievable within constraints
- [[09-DESIGN|09 — Design]]: Detailed design translates requirements into technical specifications
- [[10-IMPLEMENTATION|10 — Implementation]]: Requirements serve as the contract for what developers must build
- [[11-TESTING|11 — Testing]]: Test cases are derived directly from requirements acceptance criteria
- [[12-DEPLOYMENT|12 — Deployment]]: Requirements define what must be verified in production environments
- [[01-START-HERE|00 — START-HERE]]: Foundational concepts that apply across all phases
- [[47-SENIOR-ENGINEERING-AND-RETROSPECTIVE|47 — SENIOR ENGINEERING AND RETROSPECTIVE]]: Lessons learned from requirements processes inform future improvements