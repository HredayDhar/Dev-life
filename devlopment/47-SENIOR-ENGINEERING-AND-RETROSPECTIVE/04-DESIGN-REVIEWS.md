# 04 — Design Reviews

## 1. What Is This?

Design reviews are structured evaluations of technical designs, architectures, or implementations before significant investment in implementation. They provide a forum for stakeholders to examine proposed solutions, identify potential issues, suggest improvements, and ensure alignment with technical standards, business requirements, and organizational goals. Effective design reviews catch problems early when they're least expensive to fix and promote knowledge sharing across the team.

## 2. Why Does It Matter

Well-conducted design reviews directly impact:
- **Early Issue Detection**: Catching architectural flaws, scalability issues, or missing requirements before coding begins
- **Knowledge Transfer**: Spreading understanding of system components and design decisions across the team
- **Consistency Enforcement**: Ensuring adherence to established patterns, standards, and best practices
- **Risk Reduction**: Identifying potential performance, security, or maintenance problems early
- **Collaboration Improvement**: Creating forums for cross-functional input and buy-in
- **Decision Documentation**: Recording rationale for architectural choices for future reference
- **Mentoring Opportunity**: Junior engineers learn from senior engineers' feedback and questions
- **Innovation Balance**: Evaluating novel approaches against proven solutions
- **Resource Optimization**: Preventing wasted effort on flawed approaches
- **Stakeholder Alignment**: Ensuring technical solutions meet business needs
- **Quality Culture**: Reinforcing that thoughtful design precedes implementation
- **Technical Debt Prevention**: Avoiding shortcuts that create long-term maintenance burdens

## 3. Types of Design Reviews

### Architecture Reviews
- Focus on high-level system structure and component interactions
- Evaluate scalability, reliability, and technology choices
- Assess integration with existing systems and future extensibility
- Typically involve architects, tech leads, and senior engineers

### Component/Service Design Reviews
- Examine individual services, modules, or major components
- Review interfaces, data models, and internal architecture
- Consider performance characteristics and failure modes
- Involve developers who will implement and maintain the component

### API/Interface Reviews
- Focus on public contracts between systems or components
- Evaluate usability, versioning strategy, and error handling
- Assess documentation completeness and clarity
- Include both producers and consumers of the API

### Security Reviews
- Specialized focus on authentication, authorization, data protection
- Evaluate threat models and mitigation strategies
- Assess compliance with security policies and regulations
- Involve security engineers or specialists when available

### Performance Reviews
- Concentrate on latency, throughput, and resource utilization
- Review algorithms, data structures, and scaling approaches
- Evaluate caching strategies and database query patterns
- May involve performance specialists or SREs

### Data Model Reviews
- Focus on database schemas, data flow, and consistency guarantees
- Evaluate normalization, indexing strategies, and migration plans
- Assess data quality, validation, and evolution approaches
- Include data engineers or database administrators

## 4. When to Conduct Design Reviews

Design reviews are most valuable for:
- **New Major Features**: Significant functionality affecting multiple components
- **Architectural Changes**: Modifications to system structure or technology choices
- **Public APIs/Interfaces**: Contracts that will be consumed by other teams
- **Complex Algorithms**: Non-trivial logic with performance or correctness implications
- **Data Model Changes**: Schema modifications affecting storage or reporting
- **Third-Party Integrations**: Dependencies on external systems or services
- **Security-Sensitive Features**: Authentication, authorization, or data protection
- **Performance-Critical Components**: Areas with strict latency or throughput requirements
- **Refactoring Efforts**: Major restructuring of existing code
- **Technology Adoption**: Introduction of new frameworks, languages, or infrastructure

Less formal reviews may suffice for:
- **Small, Isolated Features**: Minimal impact on existing systems
- **Bug Fixes**: Straightforward corrections with clear scope
- **Experimental/Spike Work**: Throwaway exploration to validate assumptions
- **Well-Understood Enhancements**: Minor improvements to existing patterns

## 5. Design Review Process

### Preparation (Presenter)
1. **Define Scope**: Clearly articulate what is being reviewed and what decisions are needed
2. **Gather Context**: Collect requirements, constraints, and relevant background information
3. **Create Artifacts**: Prepare diagrams, documents, or prototypes to explain the design
4. **Identify Stakeholders**: Determine who needs to participate based on impact and expertise
5. **Schedule Appropriately**: Allow sufficient time for review and discussion
6. **Distribute Materials**: Share review materials in advance for pre-reading
7. **Prepare Questions**: Anticipate areas of concern or uncertainty

### Conducting the Review (Facilitator)
1. **Set Context**: Explain the problem being solved and review objectives
2. **Present the Design**: Walk through the proposed solution with visual aids
3. **Encourage Questions**: Create an environment where all questions are welcome
4. **Focus on Key Areas**: Guide discussion toward scalability, performance, security, etc.
5. **Manage Time**: Keep discussion focused and within allocated time
6. **Capture Feedback**: Document issues, questions, and action items
7. **Summarize Decisions**: Clearly state conclusions and next steps
8. **Assign Action Items**: Specify who will do what by when

### Participation (Reviewers)
1. **Read Materials in Advance**: Come prepared with questions and observations
2. **Focus on Impact Areas**: Prioritize scalability, maintainability, and risk factors
3. **Ask Clarifying Questions**: Ensure understanding before critiquing
4. **Balance Critique with Recognition**: Acknowledge strengths as well as weaknesses
5. **Consider Multiple Perspectives**: Think about operators, security, and future maintainers
6. **Respect Time Constraints**: Stay focused on review objectives
7. **Document Findings**: Record specific issues with suggested resolutions
8. **Voice Concerns Respectfully**: Frame feedback constructively

### Follow-up
1. **Address Feedback**: Update design based on review outcomes
2. **Document Decisions**: Record rationale for architectural choices
3. **Track Action Items**: Ensure follow-up on identified issues
4. **Communicate Outcomes**: Share decisions with broader stakeholders if needed
5. **Schedule Reviews**: Plan for follow-up reviews if significant changes were made
6. **Retain Materials**: Keep review artifacts for future reference and onboarding

## 6. Key Areas to Evaluate

### Functional Correctness
- Does the design fully address the stated requirements?
- Are edge cases and error conditions properly handled?
- Is the behavior well-defined for all expected inputs?
- Have assumptions been explicitly stated and validated?

### Scalability & Performance
- How will the solution perform under expected load?
- What are the bottlenecks and how do they scale?
- Are there efficient algorithms and data structures?
- Have caching strategies been considered where appropriate?

### Reliability & Fault Tolerance
- How does the system handle partial failures?
- Are there appropriate retry mechanisms and timeouts?
- Is data durability ensured where required?
- Have failure modes been considered and mitigated?

### Security & Privacy
- Are authentication and authorization properly implemented?
- Is sensitive data protected in transit and at rest?
- Have common vulnerabilities been considered (OWASP Top 10, etc.)?
- Are privacy requirements and regulations addressed?

### Maintainability & Operability
- Is the code structured for easy understanding and modification?
- Are there appropriate logging, monitoring, and alerting hooks?
- How easy will it be to debug issues in production?
- Have deployment and rollback procedures been considered?

### Testability
- Can the solution be effectively unit tested?
- Are there clear integration test strategies?
- Have testability hooks been considered where needed?
- Are there sufficient observability Points for troubleshooting?

### Compliance & Standards
- Does the design adhere to organizational coding standards?
- Are there any regulatory or compliance requirements to consider?
- Have accessibility requirements been addressed where applicable?
- Are licensing considerations properly handled for dependencies?

### Interoperability
- How will the new component integrate with existing systems?
- Are interfaces well-defined and versioned appropriately?
- Have backward compatibility concerns been addressed?
- Are communication protocols and data formats appropriate?

### Resource Efficiency
- What are the memory, CPU, storage, and network requirements?
- Have resource usage patterns been considered and optimized?
- Are there opportunities for sharing or pooling resources?
- Have costs been estimated and aligned with budget expectations?

## 7. Effective Review Techniques

### Question-Driven Approach
- Prepare probing questions in advance about key concerns
- Use Socratic questioning to uncover assumptions
- Ask "how" and "why" questions to explore rationale
- Challenge assumptions gently but persistently
- Focus on discovery rather than judgment

### Perspective-Taking
- Examine the design from different stakeholder viewpoints:
  - End-user perspective (usability, performance)
  - Operator perspective (monitoring, debugging)
  - Security perspective (threats, vulnerabilities)
  - Future maintainer perspective (clarity, documentation)
  - Business perspective (cost, time-to-market, flexibility)

### Scenario-Based Evaluation
- Walk through typical usage scenarios
- Consider edge cases and failure conditions
- Evaluate performance under peak load conditions
- Assess behavior during dependency outages
- Test mental models against exceptional circumstances

### Comparison with Alternatives
- Ask what alternative approaches were considered
- Evaluate the trade-offs that led to the chosen solution
- Consider simpler solutions that might suffice
- Examine whether the design solves the right problem

### Pattern Recognition
- Compare against established architectural patterns
- Identify deviations from organizational standards
- Look for opportunities to reuse existing solutions
- Assess whether innovations are justified by benefits

## 8. Common Pitfalls to Avoid

### For Presenters
- **Over-Preparing**: Spending too much time on perfect slides instead of substance
- **Defensiveness**: Taking criticism personally instead of learning from it
- **Insufficient Context**: Failing to explain why the problem matters
- **Scope Creep**: Allowing the review to drift into unrelated areas
- **Ignoring Feedback**: Not addressing legitimate concerns raised
- **Unpreparedness**: Coming without adequate preparation or anticipation of questions
- **Monologuing**: Talking too much without leaving room for discussion
- **Vagueness**: Not being specific enough about trade-offs and decisions

### For Reviewers
- **Bike-Shedding**: Spending disproportionate time on trivial details
- **Negativity Bias**: Focusing only on problems without acknowledging strengths
- **Lack of Preparation**: Coming unprepared and wasting everyone's time
- **Personal Preferences**: Elevating stylistic preferences to architectural issues
- **Groupthink**: Going along with consensus without voicing genuine concerns
- **Premature Optimization**: Focusing on performance before establishing correctness
- **Scope Expansion**: Trying to solve problems outside the review's charter
- **Inconsistent Standards**: Applying different criteria to similar designs

### For Facilitators
- **Poor Time Management**: Allowing discussions to run over or cutting off valuable input
- **Dominating Conversation**: Talking too much and not enabling others to participate
- **Ignoring Power Dynamics**: Not ensuring junior members feel safe to speak up
- **Lack of Focus**: Letting discussion drift without guiding toward objectives
- **Inadequate Follow-up**: Not capturing action items or ensuring they're addressed
- **Psychological Safety Issues**: Creating environments where people fear speaking up
- **Missing Stakeholders**: Not including people whose expertise is needed
- **Inappropriate Timing**: Scheduling reviews when key people are unavailable or rushed

## 9. Design Review Artifacts

### Essential Documents
- **Problem Statement**: Clear description of the problem being solved
- **Goals and Non-Goals**: What is and isn't in scope
- **Requirements**: Functional and non-functional requirements
- **Constraints**: Technical, temporal, resource, or organizational limitations
- **Assumptions**: Explicit statements about conditions believed to be true
- **Proposed Solution**: Detailed description of the design
- **Alternatives Considered**: Other approaches that were evaluated and rejected
- **Trade-off Analysis**: Explicit evaluation of competing qualities
- **Open Questions**: Issues that need further investigation
- **Action Items**: Follow-up tasks from the review

### Visual Aids
- **Component Diagrams**: Boxes-and-arrows showing system structure
- **Sequence Diagrams**: Illustrating interactions over time
- **Data Flow Diagrams**: Showing how data moves through the system
- **State Diagrams**: Modeling behavior across different conditions
- **Deployment Diagrams**: Showing physical infrastructure arrangement
- **UI Mockups**: For user-facing components
- **API Specifications**: Contract definitions for interfaces
- **Data Models**: Schemas for persistent storage

### Supporting Materials
- **Performance Calculations**: Estimates of load, latency, resource usage
- **Security Threat Models**: Potential attack vectors and mitigations
- **Cost Estimates**: Infrastructure, licensing, or operational expenses
- **Migration Plans**: How to transition from existing to new solution
- **Rollback Procedures**: How to revert if problems arise
- **Testing Strategy**: Approach to validating correctness and performance
- **Monitoring Plan**: What will be observed and alerted on

## 10. Integrating Design Reviews into Development Process

### Trigger Points
- **Before Major Implementation**: Significant investment of engineering time
- **At Milestone Gates**: End of discovery or exploration phases
- **When Introducing New Patterns**: First use of a new architectural approach
- **Prior to Technology Adoption**: Before committing to new frameworks or tools
- **When Crossing Team Boundaries**: Features requiring coordination across teams
- **After Prototyping**: Once exploratory work indicates a promising direction
- **Before Public Commitments**: Before making promises to stakeholders or customers

### Process Integration
- **Definition of Ready**: Include design review completion as a criterion
- **Sprint Planning**: Allocate time for preparation and participation
- **Retrospectives**: Review effectiveness of design review process
- **Metrics Tracking**: Measure review frequency, defect prevention, etc.
- **Continuous Improvement**: Regularly refine the review process based on feedback
- **Training**: Provide guidance on effective review participation
- **Tooling**: Use collaborative documents, version-controlled diagrams, etc.
- **Communities of Practice**: Share lessons learned across review experiences

### Scaling Approaches
- **Lightweight Reviews**: For lower-risk changes, use async comments or quick syncs
- **Review Templates**: Standardized formats for common review types
- **Review Rotations**: Share facilitation and presentation responsibilities
- **Expert Reviewers**: Involve specialists for security, performance, etc.
- **Hierarchical Reviews**: Team-level reviews followed by org-level for major initiatives
- **Communities of Practice**: Domain-specific reviews for frontend, backend, data, etc.
- **Open Office Hours**: Drop-in times for informal design feedback

## 11. Measuring Design Review Effectiveness

### Leading Indicators
- **Review Frequency**: Percentage of significant work that undergoes review
- **Preparation Quality**: Completeness and clarity of review materials
- **Participation Rates**: Attendance and engagement of invited stakeholders
- **Action Item Creation**: Number of concrete improvements identified per review
- **Pre-Read Compliance**: Percentage of reviewers who materials in advance
- **Time Efficiency**: Ratio of review duration to value gained

### Lagging Indicators
- **Defect Prevention**: Reduction in design-related bugs found in testing/production
- **Rework Reduction**: Decrease in major redesigns during implementation
- **Knowledge Sharing**: Increased cross-team understanding of systems
- **Standard Adoption**: Improved consistency with architectural guidelines
- **Decision Quality**: Fewer reversed or significantly altered decisions post-review
- **Onboarding Speed**: Reduced time for new engineers to become productive
- **Innovation Balance**: Appropriate adoption of new technologies and patterns
- **Stakeholder Satisfaction**: Feedback from those participating in reviews

### Qualitative Feedback
- **Reviewer Surveys**: Perceived value and effectiveness of reviews
- **Presenter Feedback**: Usefulness of feedback received
- **Observed Behaviors**: Changes in how teams approach design discussions
- **Incident Analysis**: Whether reviewed designs had fewer production issues
- **Mentoring Impact**: Growth in junior engineers' design capabilities

## 12. Special Considerations

### Remote/Hybrid Reviews
- **Video Conferencing**: Ensure everyone can see and be heard clearly
- **Shared Documents**: Use collaborative editing for real-time annotations
- **Explicit Turn-Taking**: Prevent talking over each other in virtual settings
- **Breakout Rooms**: For large reviews, divide into focused discussion groups
- **Asynchronous Options**: Allow comments and questions over extended periods
- **Recording Considerations**: Balance knowledge sharing with psychological safety
- **Time Zone Sensitivity**: Schedule to accommodate distributed team members

### Large/Complex Reviews
- **Pre-Review Circulation**: Distribute materials well in advance for digestion
- **Staggered Sessions**: Break into multiple focused meetings
- **Supplemental Materials**: Provide background reading or tutorials
- **Expert Presenters**: Have specialists lead sections on their domains
- **Structured Agenda**: Allocate time to specific topics or concerns
- **Decision Framework**: Use explicit criteria for evaluating options
- **Facilitator Preparation**: Extra effort needed to manage complexity

### Cross-Functional Reviews
- **Shared Glossary**: Ensure common understanding of terms and acronyms
- **Educational Components**: Brief explanations of domain-specific concepts
- **Respect for Expertise**: Value different types of knowledge equally
- **Translation Efforts**: Help technical and non-technical participants understand each other
- **Joint Problem-Solving**: Frame as collaborative solution-finding rather than evaluation
- **Outcome Focus**: Keep sight of shared business objectives
- **Follow-Up Mechanisms**: Ensure agreed actions happen across team boundaries

### Reviews with External Parties
- **NDA Considerations**: Protect confidential information appropriately
- **Intellectual Property**: Clarify ownership and usage rights
- **Presentation Preparation**: Extra polish for external audiences
- **Cultural Sensitivity**: Be aware of different communication styles
- **Logistics Planning**: Account for travel, time zones, and technical setup
- **Follow-Up Coordination**: Establish clear communication channels post-review
- **Relationship Building**: Use reviews as opportunities to strengthen partnerships

## 13. Evolving Your Design Review Practice

### Maturity Progression
- **Ad Hoc**: Reviews happen inconsistently based on individual initiative
- **Informal**: Regular but unstructured discussions of designs
- **Structured**: Defined process with templates and roles
- **Optimized**: Data-driven refinement based on metrics and feedback
- **Integrated**: Seamlessly woven into development lifecycle
- **Influential**: Shaping organizational standards and practices

### Continuous Improvement
- **Retrospective Reviews**: Periodically examine the review process itself
- **Benchmarking**: Compare against industry practices or high-performing teams
- **Experimentation**: Try new formats, frequencies, or participant mixes
- **Feedback Loops**: Actively seek input on how to improve reviews
- **Training Investment**: Develop review skills through practice and coaching
- **Tooling Evaluation**: Assess whether new tools could enhance the process
- **Knowledge Capture**: Systematically extract lessons from reviews
- **Teaching Others**: Deepen understanding by coaching new reviewers

###Adapting to Context
- **Startup vs. Enterprise**: Different formality levels based on risk tolerance and speed needs
- **Regulated Industries**: Increased focus on compliance and auditability
- **Open Source Projects**: Asynchronous reviews with broader community participation
- **Consulting Environments**: Client education and expectation management components
- **Research Settings**: Balance exploration with rigor and reproducibility
- **Legacy System Modernization**: Special attention to migration and cutover plans
- **Greenfield Projects**: Greater freedom to innovate balanced with foundation building
- **Crisis Response**: Accelerated processes while maintaining essential safeguards

## 14. Conclusion

Design reviews are a powerful lever for improving software quality, team collaboration, and organizational learning. By investing time in thoughtful evaluation before implementation, teams can avoid costly mistakes, spread knowledge more effectively, and build systems that are better aligned with both technical excellence and business needs. The most effective design review cultures balance rigor with agility, ensuring that reviews add value without becoming bureaucratic obstacles. Like any engineering practice, design review effectiveness comes from consistent application, continuous refinement, and a genuine commitment to building better software through collective wisdom.