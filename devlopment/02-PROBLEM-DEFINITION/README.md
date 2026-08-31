# Phase 02 — PROBLEM-DEFINITION

## 1. Purpose

The purpose of the Problem Definition phase is to clearly articulate the problem that needs to be solved, understand who experiences this problem, quantify its impact, and define what success looks like. This phase transforms vague ideas or complaints into a well-defined problem statement that can guide the entire software development process.

## 2. What This Phase Is

Problem Definition is the process of moving from a general awareness of an issue to a precise, evidence-based description of what the problem is, who it affects, how it manifests, and why it matters. This phase involves gathering data, talking to affected stakeholders, analyzing the current situation, and articulating the gap between the current state and the desired state.

## 3. Why This Phase Exists

Building software to solve the wrong problem is one of the most expensive mistakes in development. Problem Definition exists to:
- Ensure we're solving the right problem before investing in solutions
- Prevent solutioneering (jumping to solutions before understanding the problem)
- Create alignment among stakeholders about what needs to be fixed
- Provide a foundation for requirements gathering and design decisions
- Enable measurement of whether our solution actually addresses the problem

## 4. Where It Fits in the Software Development Lifecycle

Problem Definition follows Project Intake and precedes Business Understanding and User Research. It takes the high-level project concept from intake and creates the detailed problem foundation that informs all subsequent phases including requirements, design, and testing.

## 5. When This Phase Starts

This phase starts when:
- A project concept has been approved through Project Intake
- Initial stakeholders have been identified
- There's a need to move beyond vague descriptions to specific, actionable problem understanding
- Before significant resources are committed to solution design

## 6. What Must Be Known Before Starting

Before beginning Problem Definition, the team should understand:
- The high-level project idea from Project Intake
- Basic context about the domain or industry
- Who the key stakeholders are (to know who to talk to)
- Any constraints or boundaries that have been identified
- The time and resources available for problem definition activities

## 7. Inputs

Inputs to this phase include:
- Project charter or approval from Project Intake
- Initial stakeholder list
- Any existing data or anecdotes about the problem
- Business goals or objectives the project should support
- Preliminary scope boundaries

## 8. Activities

Key activities in Problem Definition include:
- Conducting stakeholder interviews to gather perspectives
- Analyzing existing data, logs, or metrics related to the problem
- Observing the problem in context (when possible)
- Creating problem statements using templates like "How might we..." or "The problem is..."
- Quantifying problem impact (frequency, severity, cost, etc.)
- Distinguishing between symptoms and root causes
- Validating the problem understanding with multiple stakeholders

## 9. Outputs / Deliverables

Outputs from this phase include:
- Clear problem statement document
- Evidence supporting the problem existence and impact
- List of affected stakeholders and their perspectives
- Problem impact analysis (quantitative and qualitative)
- Root cause analysis (initial hypotheses)
- Success criteria or metrics for measuring problem resolution
- Updated stakeholder map based on findings

## 10. Who Is Involved

Key participants in Problem Definition:
- Product Manager or Business Analyst (usually leads)
- UX Researchers (for user-focused problems)
- Domain Experts (to understand context)
- Affected Users or Customers (primary sources)
- Technical Leads (to assess feasibility implications)
- Data Analysts (if metrics are available)
- Stakeholder Representatives (from business units)

## 11. Step-by-Step Workflow

1. **Review Project Intake Outputs**: Examine the approved project concept and initial information
2. **Identify Problem Sources**: Determine who experiences the problem and where to find evidence
3. **Gather Stakeholder Perspectives**: Conduct interviews with users, customers, internal stakeholders
4. **Collect Evidence**: Look for data, logs, metrics, or observational evidence of the problem
5. **Analyze the Current State**: Document how things work today and where the problem manifests
6. **Articulate the Problem**: Create a clear, concise problem statement using evidence
7. **Quantify Impact**: Measure the problem's effects in terms users and business care about
8. **Explore Root Causes**: Use techniques like 5 Whys or fishbone diagrams to understand underlying causes
9. **Validate Understanding**: Share findings with stakeholders to confirm accuracy
10. **Define Success Criteria**: Establish how we'll know when the problem is solved
12. **Document Findings**: Create deliverables that capture the problem definition for next phases

## 12. Real-World Example

**Context**: A mobile banking app team notices users abandoning the loan application process.

**Problem Definition Activities**:
- Interviewed 20 users who started but didn't complete loan applications
- Analyzed app analytics showing 70% drop-off at the document upload step
- Reviewed customer service logs showing frequent complaints about document requirements
- Observed users attempting to upload documents in usability tests

**Problem Statement**: "Users attempting to apply for personal loans through our mobile app abandon the process at the document upload step because they find the requirements confusing and time-consuming, resulting in approximately 1,200 abandoned applications per month and estimated lost revenue of $240K monthly."

**Impact Quantification**:
- 70% abandonment rate at document upload (vs. 15% average for other steps)
- 1,200 abandoned applications/month based on current traffic
- Average loan value of $10,000 with 20% conversion rate = $240K potential monthly revenue loss
- Customer service receives 50+ complaints/month about document upload confusion

**Success Criteria**:
- Reduce document upload abandonment from 70% to <25%
- Increase loan application completion rate by 40%
- Decrease customer service complaints about document upload by 80%

## 13. Junior Developer Perspective

### Junior Developer Thinking
"I need to build the loan application feature as specified in the ticket."

### What Juniors Should Learn
- How to ask "why" five times to get to the root problem
- That the first problem description is often a symptom, not the root cause
- The importance of talking to actual users, not just relying on secondhand information
- How to distinguish between what users say they want and what they actually need
- That spending time understanding the problem prevents building the wrong solution

## 14. Senior Developer Perspective

### Senior Developer Thinking
"Before I write any code, I need to understand:
- Who exactly experiences this problem and in what context
- What evidence proves this problem exists and is worth solving
- What the current workarounds or alternative solutions are
- How this problem connects to larger business objectives
- What would constitute meaningful improvement vs. just incremental change
- What unintended consequences solving this problem might create"

### What Seniors Do
- Challenge assumptions about the problem in the initial request
- Seek multiple perspectives to avoid bias from vocal minorities
- Use data to quantify impact rather than relying on anecdotes
- Consider whether the problem is actually solvable via software or requires process changes
- Document not just the problem but the boundaries of what problem we're solving
- Ensure the problem statement is specific enough to guide design decisions

## 15. Common Mistakes

- **Solutioneering**: Jumping to solutions before fully understanding the problem
- **Assuming**: Treating assumptions as facts without validation
- **Vocal Minority Bias**: Listening only to the loudest complainers rather than representative users
- **Symptom Focus**: Addressing surface symptoms rather than root causes
- **Lack of Evidence**: Defining problems based on opinions rather than data
- **Scope Creep**: Letting the problem definition expand beyond reasonable bounds
- **Stakeholder Exclusion**: Missing key user segments or stakeholder perspectives
- **Ignoring Context**: Not considering the environment or workflow where the problem occurs

## 16. Risks

- **Misdiagnosis**: Incorrectly identifying the problem, leading to wasted development effort
- **Analysis Paralysis**: Spending too much time defining the problem and delaying solution work
- **Stakeholder Disagreement**: Different stakeholders having conflicting views of the problem
- **Changing Conditions**: The problem evolving during the definition process
- **Evidence Gaps**: Lacking sufficient data to confidently define the problem
- **Bias Introduction**: Researchers' biases influencing problem interpretation

## 17. Security Considerations

While Problem Definition is primarily about understanding issues, security considerations include:
- Ensuring problem definition activities don't expose sensitive user data
- Considering whether the problem definition process itself could create security risks (e.g., interviewing users about vulnerabilities)
- Identifying if the problem has security implications (e.g., a problem that could be exploited)
- Documenting any security-related aspects of the problem that need to be addressed in the solution
- Considering privacy implications when gathering problem data from users

## 18. Performance Considerations

Performance considerations in Problem Definition:
- Understanding if the problem manifests differently under various load conditions
- Identifying performance-related symptoms of the problem (e.g., slow response times causing user frustration)
- Considering whether performance issues are part of the root problem or symptoms
- Ensuring problem definition activities don't inadvertently impact system performance being measured
- Documenting performance expectations as part of success criteria

## 19. Scalability Considerations

Scalability considerations:
- Understanding whether the problem scales with user growth or data volume
- Identifying if the problem is more pronounced at scale (e.g., only visible with thousands of concurrent users)
- Considering whether potential solutions would introduce scalability challenges
- Ensuring problem definition accounts for future growth projections
- Distinguishing between problems that affect all users equally vs. those that impact specific segments disproportionately

## 20. Quality Considerations

Quality considerations in Problem Definition:
- Ensuring the problem statement is clear, unambiguous, and actionable
- Validating that evidence supports the problem claims
- Checking that the problem is significant enough to warrant investment
- Verifying that the problem aligns with organizational goals and values
- Ensuring problem definition activities follow ethical research practices
- Confirming that the problem definition enables effective requirements gathering

## 21. Definition of Done

The Problem Definition phase is complete when:
- [ ] A clear, evidence-based problem statement has been created
- [ ] The problem's impact has been quantified using relevant metrics
- [ ] Affected stakeholders have been identified and their perspectives understood
- [ ] Root cause hypotheses have been formulated based on evidence
- [ ] Success criteria for problem resolution have been defined
- [ ] Findings have been validated with key stakeholders
- [ ] The problem definition enables clear requirements derivation
- [ ] Documentation captures sufficient detail for the next phase (Business Understanding)

## 22. Completion Checklist

- [ ] Problem statement written in format: "The problem is [what] affecting [who] resulting in [impact]"
- [ ] Evidence collected from multiple sources (interviews, data, observation)
- [ ] Stakeholder interviews conducted with representative users
- [ ] Impact quantified in business-relevant terms (revenue, cost, time, satisfaction)
- [ ] Root cause analysis performed (5 Whys, fishbone, etc.)
- [ ] Alternative explanations considered and ruled out
- [ ] Success criteria defined with measurable targets
- [ ] Findings reviewed and validated with stakeholders
- [ ] Problem boundaries clearly defined (what's in scope vs. out of scope)
- [ ] Documentation stored where accessible to requirements and design teams

## 23. Related Phases

- **01-Project Intake**: Provides the initial project concept that gets refined here
- **03-Business Understanding**: Builds on problem definition to understand business context and objectives
- **04-Stakeholders**: Identifies stakeholders whose perspectives inform problem definition
- **05-User Research**: Often conducted in parallel or immediately after to deepen user understanding
- **06-User Personas**: Created based on stakeholder and user insights from problem definition
- **07-Requirements**: Transforms the problem definition into specific, actionable requirements
- **15-Risk Management**: Uses problem understanding to identify project risks
- **16-Technical Feasibility**: Informed by problem definition to assess solution approaches