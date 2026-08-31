# 01 — PROBLEM STATEMENT

## 1. What Is This?

A problem statement is a clear, concise description of the issue that needs to be addressed by a software project. It articulates the gap between the current state and the desired state, providing focus for the entire development effort. A well-crafted problem statement avoids mentioning solutions and instead focuses purely on describing the problem itself.

## 2. Why Does It Matter?

The problem statement serves as the North Star for software development:
- Keeps the team focused on solving the right problem throughout the lifecycle
- Prevents scope creep by providing a clear boundary for what's in scope
- Enables alignment among stakeholders with different perspectives
- Provides a basis for measuring success - if the problem statement isn't solved, the project hasn't succeeded
- Saves time and money by preventing teams from building solutions to misunderstood or incorrect problems

## 3. What Problem Does It Solve?

Without a clear problem statement, teams commonly experience:
- Building elegant solutions to the wrong problems
- Misaligned efforts where different team members understand the problem differently
- Difficulty prioritizing features or making trade-off decisions
- Inability to determine when a project is complete or successful
- Wasted effort on features that don't address the core issue
- Communication breakdowns between business and technical teams

## 4. When Should We Use It?

A problem statement should be created:
- At the beginning of any software development initiative
- After initial problem discovery but before solution design
- When stakeholders have conflicting views about what needs to be fixed
- Before significant resources are allocated to development
- Whenever encountering symptoms that might indicate deeper issues
- As part of continuous improvement processes to address recurring problems

## 5. When Should We NOT Use It?

While problem statements are generally useful, avoid formal problem statements when:
- Dealing with exploratory research where the problem space is not yet defined
- Working on pure innovation projects where the goal is discovery rather than problem-solving
- Addressing extremely well-understood problems where everyone shares the same mental model
- In emergency situations requiring immediate action (though a retroactive problem statement is still valuable)
- The issue is actually a solution in disguise (e.g., "we need a mobile app" is a solution, not a problem)

## 6. Core Concepts

### Characteristics of Effective Problem Statements
- **User-centered**: Focuses on people experiencing the problem, not technical details
- **Specific**: Clearly defines who, what, when, where, and how much
- **Evidence-based**: Supported by data, observations, or stakeholder input
- **Solution-free**: Does not suggest or imply specific solutions
- **Measurable**: Includes criteria that can be used to determine when resolved
- **Actionable**: Provides clear direction for what needs to be investigated or built

### Common Problem Statement Frameworks
1. **The “_statement_** format: 
   - "The problem of _[issue]_ affects _[stakeholder group]_, resulting in _[impact/consequence]_"
   
2. **The “How might we…” format** (from design thinking):
   - "How might we _[desired outcome]_ for _[user group]_ when _[situation/context]_?"

3. **The “Before-After-Bridge” format**:
   - "Before: _[current undesirable situation]_
    After: _[desired situation]_
    Bridge: _[what needs to happen to get from before to after]_"

4. **The “5 Whys” derived statement**:
   - Based on root cause analysis, stating the fundamental problem uncovered

## 7. Step-by-Step Process

1. **Gather Initial Information**: Collect all known facts, complaints, observations, and data about the issue
2. **Talk to Affected People**: Interview users, customers, or stakeholders who experience the problem
3. **Look for Evidence**: Find data, logs, metrics, or observational proof of the problem's existence and impact
4. **Distinguish Symptom from Cause**: Determine if what you're seeing is the root problem or a symptom
5. **Identify Stakeholders**: Determine who is affected by the problem and who cares about its resolution
6. **Quantify Impact**: Measure the problem's effects in meaningful units (time, money, satisfaction, etc.)
7. **Draft the Statement**: Write a preliminary problem statement using one of the frameworks
8. **Validate with Stakeholders**: Share drafts with affected parties to ensure accuracy and completeness
9. **Refine Based on Feedback**: Incorporate stakeholder input to improve clarity and accuracy
10. **Finalize and Communicate**: Distribute the final problem statement to the entire project team

## 8. Inputs

Inputs to creating a problem statement include:
- Stakeholder interview transcripts or notes
- Customer support tickets or complaints
- System logs, metrics, or monitoring data
- User feedback from surveys or usability tests
- Observational notes from field studies
- Competitive analysis or market research
- Regulatory or compliance requirements
- Business goals or objectives documentation
- Previous project post-mortems or retrospectives
- Domain expertise and contextual knowledge

## 9. Outputs / Deliverables

The primary output is a documented problem statement, typically including:
- One or two sentence core problem statement
- Supporting evidence and data points
- Affected stakeholder groups identified
- Impact quantification (where possible)
- Boundaries clarifying what aspects of the problem are in scope
- Assumptions made during problem formulation
- Open questions requiring further investigation
- Visual representations (when helpful) like process maps or user journey snippets

## 10. Real-World Example

**Context**: An e-commerce company notices declining conversion rates on their mobile website.

**Initial Complaint**: "Our mobile website conversion rate is too low."

**Investigation Findings**:
- Mobile conversion rate: 1.2% vs. desktop: 3.8% (68% lower)
- 75% of mobile users abandon during checkout process
- Customer service complaints about mobile checkout increased 200% QoQ
- Session recordings show users struggling with form fields and button sizes
- Page load time averages 4.8 seconds on mobile vs. 2.1 seconds on desktop

**Poor Problem Statement** (solution-focused):
"We need to build a faster mobile checkout page with larger buttons."

**Good Problem Statement** (problem-focused):
"Mobile users attempting to complete purchases on our e-commerce site abandon their carts during checkout at a rate of 75%, compared to 35% on desktop, resulting in approximately $1.2M in lost monthly revenue due to usability difficulties with form inputs, slow page loading, and unclear progress indication during the checkout process."

**Evidence Supporting Statement**:
- Analytics data showing 75% abandonment rate at mobile checkout
- Revenue calculation: 100K monthly mobile sessions × 75% abandonment × $40 AOV = $3M potential, capturing 40% of that = $1.2M monthly loss
- Usability testing showing specific pain points with form fields and buttons
- Performance testing confirming load time differences
- Customer service complaint trends

## 11. Technical Example

**Context**: A SaaS platform experiences periodic slowdowns affecting all users.

**Initial Observation**: "The application is sometimes slow."

**Investigation Findings**:
- Response times increase from normal 200ms to 5000+ms during incidents
- Incidents occur approximately 3 times per week, lasting 15-45 minutes each
- During incidents, CPU usage on database servers spikes to 95%+
- Application logs show increased timeout errors from frontend services
- User surveys indicate 40% of users consider switching providers due to reliability concerns
- Business estimates each incident costs approximately $15K in lost productivity and potential churn

**Problem Statement**:
"Our SaaS platform experiences periodic performance degradation where response times increase from 200ms to over 5 seconds occurring approximately 3 times weekly, resulting in user frustration, potential churn affecting 40% of our user base, and estimated business impact of $45K weekly due to database CPU saturation causing timeout errors across frontend services during peak usage periods."

## 12. Good Approach

**Good Problem Statement Characteristics for the E-commerce Example**:
- **Specific**: Identifies mobile users, checkout process, specific abandonment rate
- **Measurable**: Quantifies abandonment rate (75%), revenue impact ($1.2M monthly), comparison to desktop (35%)
- **User-centered**: Focuses on user experience difficulties rather than technical implementations
- **Evidence-based**: References analytics data, user testing, customer service trends
- **Solution-free**: Does not mention specific technical solutions like "faster page" or "larger buttons"
- **Actionable**: Provides clear areas to investigate (form inputs, page loading, progress indication)
- **Scoped**: Clearly identifies the problem as occurring during mobile checkout process

## 13. Bad Approach

**Poor Problem Statement Examples and Why They Fail**:

*"We need to improve our mobile conversion rate."* 
- **Failure reason**: States a solution need (improve) rather than describing the problem
- **Missing**: Who is affected, what specifically is problematic, evidence of the issue

*"Users hate our mobile checkout because it's slow and ugly."*
- **Failure reason**: Uses emotional language ("hate"), subjective descriptors ("slow", "ugly") without evidence
- **Missing**: Specific measurements, stakeholder quantification, boundary definition

*"Let's redesign the checkout flow to be more like Amazon's."*
- **Failure reason**: Immediately jumps to a solution (redesign) and references a competitor
- **Missing**: Problem description, evidence that current flow is problematic, user validation

*"Our mobile KPIs are not meeting targets."*
- **Failure reason**: Too vague, uses internal jargon (KPIs) without explanation
- **Missing**: Specific metrics affected, user impact, business consequences, evidence

## 14. Common Mistakes

- **Embedding Solutions**: Including phrases like "we need to build..." or "the solution is..." 
- **Being Too Vague**: Statements like "improve user experience" or "increase efficiency" without specifics
- **Using Internal Jargon**: Language that only makes sense to insiders rather than describing the user problem
- **Focusing on Symptoms**: Describing what you see rather than the underlying problem (e.g., "users click back button" vs "users can't find needed information")
- **Making Assumptions**: Stating beliefs as facts without evidence ("users find it confusing" without testing)
- **Being Too Broad**: Attempting to solve multiple unrelated problems in one statement
- **Ignoring Stakeholders**: Defining the problem from only one perspective (usually internal) rather than user-focused
- **Lacking Measurement**: Not including any way to determine when the problem is solved
- **Being Negative-Focused Only**: Only describing what's wrong without suggesting what better would look like
- **Using Passive Voice**: Making the problem seem to exist without clear ownership or causation

## 15. Security Considerations

While creating problem statements is primarily analytical, security considerations include:
- Ensuring that problem discovery activities don't inadvertently expose sensitive data or system vulnerabilities
- Considering whether the problem has security implications (e.g., a problem that could be exploited for unauthorized access)
- Documenting if sensitive customer or business data is involved in the problem context
- Considering privacy implications when gathering problem information from users
- Identifying if the problem relates to compliance requirements (GDPR, HIPAA, PCI-DSS, etc.)
- Ensuring that evidence gathering follows organizational security policies
- Considering whether potential solutions might introduce new security considerations that should be noted

## 16. Performance Considerations

Performance considerations in problem statement creation:
- Understanding if the problem varies under different load conditions (e.g., only appears during peak usage)
- Identifying whether performance issues are the core problem or symptoms of other issues
- Ensuring that problem investigation activities don't inadvertently degrade system performance being measured
- Considering whether the problem statement should include performance thresholds or expectations
- Documenting if the problem has different manifestations under various environmental conditions
- Ensuring that performance metrics used to quantify the problem are reliable and meaningful
- Considering scalability aspects - does the problem get worse with more users, data, or transactions?

## 17. Scalability Considerations

Scalability considerations for problem statements:
- Determining if the problem scales linearly with user growth or has threshold effects
- Identifying if the problem only manifests at certain scales (e.g., only visible with 10K+ concurrent users)
- Considering whether describing the problem should include scalability thresholds or limitations
- Ensuring that evidence gathering accounts for different usage patterns and scales
- Understanding if the problem affects all users equally or disproportionately impacts certain segments at scale
- Considering whether the problem statement should distinguish between current scale and future growth projections
- Documenting any known scaling limitations or bottlenecks that contribute to the problem

## 18. Maintainability Considerations

Maintainability considerations in problem formulation:
- Ensuring the problem statement is written in language that will remain understandable over time
- Avoiding references to specific temporary conditions or events that may change
- Considering whether the problem is likely to evolve or require updates as the system changes
- Making sure the problem statement focuses on fundamental user needs rather than temporary manifestations
- Ensuring that the problem statement enables sustainable solution development rather than quick fixes
- Considering whether the problem statement should account for technical debt or legacy system constraints
- Making sure the problem statement is specific enough to guide long-term architectural decisions

## 19. Junior Developer Approach

**How Junior Developers Typically Approach Problem Statements**:
- Often jump directly to suggesting solutions when asked about problems
- May focus on technical details they find interesting rather than user impact
- Tend to rely on assumptions or secondhand information rather than direct user contact
- Might create overly broad problem statements that try to solve everything at once
- Frequently miss the importance of quantifying impact in business terms
- May struggle to distinguish between symptoms and root causes
- Often create problem statements that reflect their technical perspective rather than user perspective

**What Juniors Should Learn**:
- Practice active listening to understand problems from the user's perspective
- Learn to ask "why" multiple times to get to root causes
- Develop skills in gathering and interpreting different types of evidence (qualitative and quantitative)
- Understand that time spent understanding the problem prevents wasted development effort
- Learn to quantify problems in terms that matter to the business (revenue, cost, time, satisfaction)
- Practice writing solution-free descriptions that focus purely on the problem
- Develop empathy for users by spending time understanding their context and workflows
- Learn to validate problem understanding with multiple stakeholders before proceeding

## 20. Senior Developer Approach

**How Senior Developers Think About Problem Statements**:
- Automatically question whether the presented issue is the real problem or a symptom
- Immediately consider what evidence would be needed to validate the problem understanding
- Think about boundaries - what aspects of the problem are in scope vs. out of scope
- Consider multiple stakeholder perspectives and potential conflicts between them
- Think about how the problem connects to larger business objectives and strategy
- Consider long-term implications - will solving this problem create new issues or technical debt?
- Think about measurement - how will we know when the problem is truly solved?
- Consider the problem's context - what environmental factors influence its manifestation?

**What Seniors Do**:
- Challenge initial problem descriptions by seeking multiple perspectives and data sources
- Use techniques like influence mapping to understand who cares about the problem and why
- Apply systems thinking to understand how the problem connects to other systems and processes
- Ensure problem statements are specific enough to guide architectural and design decisions
- Balance user needs with technical feasibility and business constraints
- Document assumptions and uncertainties in the problem statement
- Use problem statements as communication tools to align disparate stakeholders
- Regularly revisit and validate problem understanding as work progresses
- Consider ethical implications of both the problem and potential solutions

## 21. Senior Engineer Questions

Senior engineers should ask when developing or reviewing problem statements:
- What evidence do we have that this problem actually exists and is worth solving?
- Who experiences this problem most acutely, and whose voices might we be missing?
- What are we assuming about the problem that we haven't validated?
- How does this problem connect to our business objectives and strategy?
- What would constitute a meaningful improvement vs. just incremental change?
- What potential negative consequences could solving this problem create?
- Are we solving the root cause or just treating symptoms?
- How will we measure whether we've actually solved the problem?
- What boundaries should we set around what problem we're trying to solve?
- What assumptions are we making, and how could we test them?
- How does this problem manifest differently for different user segments?
- What is the current workaround or alternative solution people are using?
- What would happen if we did nothing about this problem?
- How problem is this problem compared to other issues we could be working on?

## 22. Practical Exercise

**Exercise**: Create a problem statement for a hypothetical situation.

**Scenario**: Your team receives a request: "We need to build a new feature that lets users export their data in PDF format."

**Instructions**:
1. Resist the urge to jump to the solution (PDF export feature)
2. Ask questions to understand why this feature is being requested
3. Imagine you've investigated and found the following:
   - Users currently take screenshots of their data and manually combine them into documents
   - Support tickets show 50+ monthly requests for better data export options
   - Power users spend approximately 2 hours per week manually creating reports from system data
   - Competitor analysis shows 3 of 5 top competitors offer one-click export functionality
   - Sales team reports losing enterprise deals due to lack of advanced reporting features
   - User surveys indicate 65% of users would pay extra for better export functionality

**Task**: Write a problem statement based on this investigation.
Then:
- Identify what makes it a good problem statement
- Note what evidence supports it
- Explain how it avoids solutioneering
- Describe how it would guide solution exploration
- Identify what assumptions you made and how you'd validate them

## 23. Definition of Done

A problem statement is considered complete when:
- [ ] It clearly describes a specific problem without suggesting solutions
- [ ] It identifies who experiences the problem and in what context
- [ ] It includes evidence supporting the problem's existence and impact
- [ ] It quantifies the problem's effects in measurable terms where possible
- [ ] It distinguishes between the core problem and symptoms
- [ ] It is written in clear, accessible language understandable to all stakeholders
- [ ] It provides sufficient detail to guide requirements gathering and solution exploration
- [ ] It has been validated with affected stakeholders or subject matter experts
- [ ] It establishes boundaries for what aspects of the problem are in scope
- [ ] It includes a way to measure whether the problem has been resolved

## 24. Checklist

- [ ] Problem statement avoids solution language (no "we need to build", "solution is", etc.)
- [ ] Statement identifies specific affected user or stakeholder groups
- [ ] Problem description includes who, what, when, where, and how much
- [ ] Evidence is cited to support problem claims (data, observations, user feedback)
- [ ] Impact is quantified in business-relevant terms (revenue, cost, time, satisfaction, etc.)
- [ ] Statement distinguishes root problem from symptoms
- [ ] Language is clear, jargon-free, and accessible to technical and non-technical audiences
- [ ] Statement provides clear direction for what needs to be investigated or built
- [ ] Problem understanding has been validated with multiple stakeholders
- [ ] Boundaries are defined (what aspects of the problem are being addressed vs. deferred)
- [ ] Success criteria or measurement approach is implied or explicit
- [ ] Statement focuses on user needs and experiences rather than technical implementations
- [ ] Assumptions are documented and identified for validation

## 25. Related Topics

- **02-WHO-HAS-THE-PROBLEM**: Understanding stakeholder perspectives and affected parties
- **03-PROBLEM-IMPACT**: Quantifying and qualifying the consequences of the problem
- **04-SUCCESS-DEFINITION**: Defining what it means for the problem to be solved
- **05-USER-RESEARCH**: Techniques for gathering user insights about problems
- **06-USER-PERSONAS**: Creating representative models of affected users
- **07-REQUIREMENTS**: Transforming problem understanding into actionable specifications
- **15-RISK-MANAGEMENT**: Using problem understanding to identify project risks
- **16-TECHNICAL-FEASIBILITY**: Assessing solution approaches based on problem definition