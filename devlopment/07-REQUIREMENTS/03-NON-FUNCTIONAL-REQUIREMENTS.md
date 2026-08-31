# 03 — NON-FUNCTIONAL REQUIREMENTS

## 1. What Are Non-Functional Requirements?

Non-functional requirements (NFRs) describe how well a system performs its functions rather than what functions it performs. While functional requirements define what the system does (features, behaviors, capabilities), non-functional requirements define the qualities, constraints, and characteristics that affect the system's operation, usability, performance, and overall user experience.

NFRs answer questions like:
- How fast should the system respond?
- How many users can it support simultaneously?
- How secure does it need to be?
- How easy is it to use and learn?
- How reliable must it be?
- How maintainable should the code be?
- How well does it scale as demand grows?

These requirements are often referred to as "quality attributes" or "system qualities" because they describe the system's properties rather than its specific behaviors. They are crucial for ensuring user satisfaction, system success, and long-term viability.

## 2. Categories of Non-Functional Requirements

Non-functional requirements span many dimensions of system quality. Here are the major categories:

### Performance Requirements
Performance requirements specify how the system behaves under various conditions in terms of speed, efficiency, and resource usage.

**Key Aspects**:
- **Response Time**: How quickly the system responds to user requests
- **Throughput**: How many transactions or requests the system can handle per unit of time
- **Resource Utilization**: How efficiently the system uses CPU, memory, disk, network, etc.
- **Scalability**: How well performance holds up as load increases
- **Latency**: Delay between request initiation and response commencement
- **Bandwidth**: Data transfer capacity
- **Startup/Shutdown Time**: How long the system takes to become operational or to shut down gracefully

**Examples**:
- "The system shall respond to 95% of user requests within 2 seconds under normal load"
- "The system shall support up to 10,000 concurrent users without degradation"
- "The system shall process batch jobs of 1 million records within 4 hours"
- "The system shall maintain 99.9% availability with planned maintenance windows not exceeding 4 hours per month"
- "The application shall launch and be ready for use within 5 seconds on supported mobile devices"
- "The system shall handle peak loads of 500 requests per second with average response time under 300ms"

### Security Requirements
Security requirements specify how the system protects information and resources from unauthorized access, disclosure, alteration, and destruction.

**Key Aspects**:
- **Authentication**: Verifying user identity
- **Authorization**: Determining what authenticated users are allowed to do
- **Data Protection**: Encrypting data at rest and in transit
- **Auditing**: Tracking who did what and when
- **Input Validation**: Preventing injection attacks and malformed data
- **Session Management**: Securely handling user sessions
- **Vulnerability Management**: Addressing known security weaknesses
- **Compliance**: Meeting regulatory and industry standards (GDPR, HIPAA, PCI-DSS, etc.)

**Examples**:
- "The system shall encrypt all personally identifiable information using AES-256 encryption at rest"
- "The system shall require multi-factor authentication for administrative access"
- "The system shall log all access to sensitive data with user ID, timestamp, and action performed"
- "The system shall prevent SQL injection and cross-site scripting attacks through input validation and output encoding"
- "The system shall automatically lock user accounts after 5 consecutive failed login attempts"
- "The system shall support role-based access control with at least 10 distinct roles"
- "The system shall undergo regular penetration testing and vulnerability scanning as part of the release process"
- "The system shall encrypt all data transmissions using TLS 1.3 or higher"

### Usability and User Experience Requirements
Usability requirements specify how easy, efficient, and satisfying the system is for users to interact with.

**Key Aspects**:
- **Learnability**: How easy it is for new users to accomplish basic tasks
- **Efficiency**: How quickly experienced users can perform tasks
- **Memorability**: How easy it is to re-establish proficiency after not using the system
- **Error Tolerance**: How well the system prevents and recovers from user errors
- **Satisfaction**: How pleasant the system is to use
- **Accessibility**: How well the system accommodates users with disabilities
- **User Interface Consistency**: How consistent the interface is across different parts of the system
- **Feedback and Guidance**: How well the system informs users about status and next steps

**Examples**:
- "New users shall be able to complete the core task of creating an account and posting their first message within 5 minutes without assistance"
- "Experienced users shall be able to perform common tasks in no more than 3 clicks or taps"
- "The system shall provide clear error messages that explain what went wrong and how to fix it"
- "The system shall comply with WCAG 2.1 AA accessibility standards"
- "The system shall maintain consistent navigation patterns across all modules"
- "The system shall provide contextual help and tooltips for all interface elements"
- "The system shall allow users to customize the interface layout and color scheme"
- "The system shall support multiple languages with UTF-8 encoding for international users"

### Reliability and Availability Requirements
Reliability requirements specify how dependable and consistently correct the system is. Availability requirements specify how often the system is operational and accessible when needed.

**Key Aspects**:
- **Mean Time Between Failures (MTBF)**: Average time the system operates correctly between failures
- **Mean Time To Repair (MTTR)**: Average time to restore service after a failure
- **Uptime Percentage**: Percentage of time the system is available and operational
- **Fault Tolerance**: Ability to continue operating correctly despite failures
- **Recovery Capability**: Ability to restore normal operation after a failure
- **Data Integrity**: Protection against data corruption or loss
- **Disaster Recovery**: Ability to resume operations after catastrophic events
- **Backup and Restore**: Capability to protect and recover data

**Examples**:
- "The system shall achieve 99.9% monthly uptime excluding scheduled maintenance windows"
- "The system shall automatically recover from single-node failures without data loss or service interruption"
- "The system shall perform automated backups hourly with point-in-time recovery to any point in the last 30 days"
- "The system shall maintain data consistency with zero tolerance for committed transaction loss"
- "The system shall detect and isolate faulty components within 30 seconds of failure occurrence"
- "The system shall support rolling updates with zero downtime for stateless services"
- "The system shall recover from a complete site failure within 4 hours with no more than 15 minutes of data loss"
- "The system shall maintain audit trails for all financial transactions for a minimum of 7 years"

### Maintainability and Supportability Requirements
Maintainability requirements specify how easy it is to modify, fix, and enhance the system. Supportability requirements specify how well the system supports ongoing operations and user assistance.

**Key Aspects**:
- **Modularity**: How well the system is divided into independent, interchangeable components
- **Code Clarity**: How easy it is to understand the source code
- **Testability**: How easy it is to test the system and isolate faults
- **Documentation Quality**: How complete and accurate the technical and user documentation is
- **Change Impact**: How localized the effects of modifications are
- **Build and Deployment**: How easy it is to compile, build, and deploy the system
- **Monitoring and Logging**: How well the system provides operational visibility
- **Diagnostic Capability**: How easy it is to troubleshoot problems
- **Upgrade Path**: How easy it is to move from one version to another
- **Vendor Support**: What level of support is provided for third-party components

**Examples**:
- "The system shall be structured using a layered architecture with clear separation of concerns"
- "All public APIs shall be documented with OpenAPI/Swagger specifications"
- "The system shall achieve at least 80% code coverage with automated unit tests"
- "The system shall support blue-green deployments to minimize release risk"
- "The system shall provide structured logging with correlation IDs for request tracing"
- "The system shall include health check endpoints for all microservices"
- "The system shall use dependency management tools with automated vulnerability scanning"
- "The system shall provide rollback capability to previous version within 10 minutes"

### Portability Requirements
Portability requirements specify how easy it is to transfer the system from one environment to another.

**Key Aspects**:
- **Platform Independence**: Ability to run on different hardware or operating systems
- **Installation Ease**: How simple it is to install and configure the system
- **Standards Compliance**: Adherence to industry standards that promote interchangeability
- **Data Portability**: Ability to export and import data in standard formats
- **Interoperability**: Ability to work with other systems and exchange information
- **Localization and Internationalization**: Ability to adapt to different languages, regions, and cultures
- **Configuration Management**: How easily system behavior can be changed through configuration

**Examples**:
- "The system shall be deployable on both Windows Server 2019+ and Linux (Ubuntu 20.04 LTS+) environments"
- "The system shall support containerization using Docker and orchestration with Kubernetes"
- "The system shall export data in standard formats including CSV, JSON, and XML"
- "The system shall import customer data from common CRM systems using predefined mapping templates"
- "The system shall support UTF-8 encoding and provide localization for at least 5 languages"
- "The system shall adhere to RESTful API design principles and JSON:API specification"
- "The system shall allow configuration changes without requiring code modifications or redeployment"
- "The system shall be installable using standard package managers (apt, yum, chocolatey)"

### Operational Requirements
Operational requirements specify how the system functions in its production environment concerning monitoring, administration, and day-to-day operations.

**Key Aspects**:
- **Monitoring Capabilities**: What metrics and health indicators the system provides
- **Alerting and Notification**: How the system communicates operational issues
- **Administrative Functions**: What tasks operators can perform to manage the system
- **Configuration Management**: How system behavior is controlled and adjusted
- **Capacity Planning**: How the system supports forecasting and resource allocation
- **Change Management**: How modifications to the system are controlled and tracked
- **Compliance Reporting**: How the system supports regulatory and internal compliance requirements
- **Environmental Considerations**: Power consumption, cooling requirements, etc.

**Examples**:
- "The system shall provide real-time dashboards showing key performance indicators (response time, error rates, throughput)"
- "The system shall send alerts via email, SMS, and Slack for critical system events"
- "The system shall maintain an audit trail of all configuration changes with user ID and timestamp"
- "The system shall support role-based administrative access with segregation of duties"
- "The system shall generate compliance reports for GDPR, SOX, and industry-specific regulations"
- "The system shall provide APIs for integrating with external monitoring and management tools"
- "The system shall log all administrative actions for security and accountability purposes"
- "The system shall support scheduled maintenance windows with user notification capabilities"

## 3. Quality Attribute Scenarios

Quality attribute scenarios are a powerful technique for specifying non-functional requirements in concrete, testable terms. They follow a specific format that makes NFRs unambiguous and measurable.

### The Quality Attribute Scenario Format
A quality attribute scenario consists of six parts:

1. **Source of Stimulus**: Who or what generates the stimulus (e.g., user, system, developer, tester)
2. **Stimulus**: The condition that arrives at the system (e.g., request, failure, change in load)
3. **Environment**: The conditions under which the stimulus occurs (e.g., normal operation, peak load, maintenance)
4. **Artifact**: The part of the system that is stimulated (e.g., database, user interface, service)
5. **Response**: The activity undertaken after the stimulus arrives (e.g., process request, recover from fault, display error)
6. **Response Measure**: How the response is measured (e.g., latency, throughput, percentage of correct responses)

### Examples of Quality Attribute Scenarios

**Performance Scenario**:
- **Source**: External user
- **Stimulus**: Submits a search request with complex filters
- **Environment**: Peak load (1000 concurrent users)
- **Artifact**: Search service
- **Response**: Processes request and returns results
- **Response Measure**: 95% of responses returned within 3 seconds

**Availability Scenario**:
- **Source**: Internal hardware (database server)
- **Stimulus**: Experiences catastrophic failure (disk corruption)
- **Environment**: Normal business hours
- **Artifact**: Database storage subsystem
- **Response**: Switches to hot standby and continues operation
- **Response Measure**: Failover completes within 30 seconds with zero data loss

**Security Scenario**:
- **Source**: External attacker
- **Stimulus**: Attempts SQL injection via login form
- **Environment**: Internet-facing production system
- **Artifact**: Authentication service
- **Response**: Rejects malicious input and logs attack attempt
- **Response Measure**: 100% of SQL injection attempts blocked; attack logged within 1 second

**Usability Scenario**:
- **Source**: Novice user
- **Stimulus**: Attempts to reset forgotten password
- **Environment**: First-time use of password reset feature
- **Artifact**: Password reset workflow
- **Response**: Guides user through reset process successfully
- **Response Measure**: 90% of users complete reset without assistance in under 2 minutes

**Modifiability Scenario**:
- **Source**: Developer
- **Stimulus**: Needs to add new payment method (Apple Pay)
- **Environment**: Scheduled maintenance window
- **Artifact**: Payment processing module
- **Response**: Implements new payment method integration
- **Response Measure**: Change implemented and tested within 8 hours; no regression in existing payment methods

### Benefits of Quality Attribute Scenarios
- **Unambiguous**: Specific, measurable criteria eliminate interpretation differences
- **Testable**: Clear pass/fail criteria enable validation
- **Contextual**: Considers real-world conditions under which requirements apply
- **Actionable**: Provides clear guidance for design and implementation decisions
- **Communicable**: Easy to explain to stakeholders across technical and business backgrounds
- **Prioritizable**: Can be ranked by business impact and implementation complexity

## 4. Techniques for Eliciting Non-Functional Requirements

### Stakeholder Interviews Focused on Quality Attributes
Specialized interviews to uncover performance, security, usability, and other quality concerns.

**Preparation**:
- Research industry standards and benchmarks relevant to the domain
- Prepare questions that explore quality dimensions (e.g., "How long would you consider acceptable to wait for this operation?")
- Identify specific quality concerns based on system type and user base
- Consider inviting specialists (performance engineers, security experts, accessibility consultants)
- Develop hypothetical scenarios to probe quality expectations

**Execution**:
- Begin with functional needs, then transition to quality expectations
- Use analogies and comparisons to elicit quality preferences ("Is this more like a sports car or a pickup truck?")
- Explore pain points with current systems related to performance, reliability, etc.
- Ask about peak usage patterns and busy periods
- Discuss trade-offs openly ("Would you prefer faster response times or lower cost?")
- Investigate regulatory and compliance drivers for security and privacy
- Explore user demographics that might affect accessibility needs
- Discuss operational concerns like monitoring, maintenance, and support needs

**Analysis**:
- Look for patterns in quality expectations across stakeholders
- Identify potential conflicts (e.g., security vs. usability)
- Note implicit assumptions about quality ("Everyone knows it needs to be fast")
- Translate qualitative descriptions into measurable criteria where possible
- Flag requirements that need specialist validation (security, performance modeling)

### Workshops and Collaborative Sessions for Quality Attributes
Structured group activities focused specifically on non-functional aspects.

**Types of NFR Workshops**:
- **Performance Modeling Workshops**: Using queuing theory or simulation to explore capacity needs
- **Security Threat Modeling**: Identifying potential threats and defining countermeasures
- **Usability Testing Planning**: Defining test scenarios and success criteria for user experience
- **Availability Design Sessions**: Exploring redundancy, failover, and disaster recovery options
- **Compliance Workshops**: Ensuring understanding of regulatory requirements and their technical implications
- **Technical Debt Assessment**: Evaluating maintainability, testability, and code quality goals
- **Scalability Planning**: Exploring horizontal vs. vertical scaling strategies

**Facilitation Techniques**:
- **Quality Attribute Tree**: Hierarchical decomposition of quality goals into specific requirements
- **Trade-Off Analysis**: Explicitly examining where improving one quality may negatively impact another
- **Benchmarking Review**: Comparing against similar systems or industry standards
- **Prototyping for Quality**: Building minimal implementations to measure specific qualities
- **Profiling Existing Systems**: Measuring current performance to establish baselines and improvements needed
- **Probing Questions**: "What happens if...?" scenarios to explore boundary conditions
- **Risk-Based Prioritization**: Focusing on qualities that pose highest risk if not adequately addressed
- **Impact Mapping**: Linking quality requirements to business goals and user benefits

### Analysis of Existing Systems and Benchmarks
Learning from current systems, competitors, and industry standards.

**Approaches**:
- **Performance Baseline Testing**: Measuring current system response times, throughput, and resource usage
- **Competitive Analysis**: Examining performance, security, and usability claims of competing products
- **Industry Standard Review**: Studying applicable standards (ISO/IEC 25010, NIST frameworks, etc.)
- **Regulatory Research**: Investigating legal requirements that impose quality constraints (GDPR, HIPAA, SOX, etc.)
- **Technology Evaluation**: Assessing performance characteristics of proposed platforms and frameworks
- **Load Testing Production Systems**: Understanding real-world behavior under actual usage patterns
- **Accessibility Audits**: Evaluating current systems against WCAG or similar guidelines
- **Security Assessments**: Reviewing current systems for vulnerabilities and protection gaps
- **Maintainability Metrics**: Analyzing code complexity, test coverage, and modification history
- **User Satisfaction Surveys**: Gathering feedback on current system usability and performance perceptions

**Analysis Techniques**:
- **Gap Analysis**: Comparing current state to desired future state for each quality attribute
- **Trend Analysis**: Identifying how quality requirements have evolved over time
- **Best Practice Extraction**: Identifying what works well in current systems that should be preserved
- **Pain Point Quantification**: Measuring frequency and impact of quality-related issues
- **Capability Mapping**: Determining what quality levels are achievable with candidate technologies
- **Cost-Benefit Analysis**: Evaluating investment needed to achieve target quality levels
- **Risk Assessment**: Identifying consequences of failing to meet quality targets
- **Dependency Analysis**: Understanding how quality attributes influence each other

### Prototyping and Simulation for Quality Validation
Using preliminary versions to test and verify quality attributes.

**Performance Prototyping**:
- **Load Testing Prototypes**: Using tools like JMeter, Gatling, or Locust to simulate user load
- **Stress Testing**: Pushing systems beyond normal capacity to identify breaking points
- **Soak Testing**: Running systems under sustained load to identify memory leaks or degradation
- **Spike Testing**: Subjecting systems to sudden bursts of load to test elasticity
- **Component Isolation Testing**: Testing individual services or modules under load
- **Network Simulation**: Testing behavior under various latency and bandwidth conditions
- **Database Performance Testing**: Evaluating query performance with realistic data volumes
- **Caching Strategy Validation**: Measuring impact of caching on response times and throughput

**Security Prototyping**:
- **Penetration Testing Prototypes**: Engaging ethical hackers to identify vulnerabilities
- **Vulnerability Scanning**: Automated testing for known security weaknesses
- **Threat Modeling Validation**: Testing proposed countermeasures against identified threats
- **Authentication Mechanism Testing**: Verifying strength and usability of login systems
- **Encryption Implementation Testing**: Verifying proper implementation and performance impact
- **Input Validation Testing**: Testing boundary conditions and malicious inputs
- **Session Security Testing**: Verifying resistance to session hijacking and fixation
- **Logging and Auditing Validation**: Ensuring sufficient detail for forensic analysis

**Usability Prototyping**:
- **Accessibility Testing**: Verifying compliance with WCAG, Section 508, or similar standards
- **Cognitive Walkthroughs**: Evaluating ease of learning and use for representative tasks
- **Heuristic Evaluations**: Expert review using established usability principles
- **User Testing Sessions**: Observing real users performing tasks with think-aloud protocol
- **A/B Testing**: Comparing different interface designs for effectiveness and preference
- **Accessibility Testing with Assistive Technologies**: Testing with screen readers, voice control, etc.
- **Internationalization Testing**: Verifying proper handling of different languages, formats, and locales
- **Mobile Responsiveness Testing**: Ensuring proper behavior across device sizes and orientations
- **Performance Usability Testing**: Measuring perceived performance versus actual measurements

**Reliability Prototyping**:
- **Chaos Engineering**: Intentionally injecting failures to test resilience
- **Failover Testing**: Verifying backup systems take over correctly
- **Data Recovery Testing**: Ensuring backups can be restored accurately and quickly
- **Network Partition Testing**: Testing behavior when system components lose connectivity
- **Resource Exhaustion Testing**: Verifying behavior when CPU, memory, or disk is depleted
- **Long-Running Stability Testing**: Testing for memory leaks or performance degradation over time
- **Disaster Recovery Testing**: Verifying ability to recover from catastrophic site loss
- **Backup Validation**: Ensuring backups are complete, consistent, and restorable

### Requirements Review and Refinement Processes
Iterative cycles to improve clarity, completeness, and quality of NFRs.

**Review Techniques**:
- **NFR Checklist Review**: Systematic evaluation against quality attribute dimensions
- **Scenario-Based Review**: Using quality attribute scenarios to test clarity and testability
- **Trade-Off Analysis Review**: Examining potential conflicts between quality requirements
- **Measurability Assessment**: Ensuring each NFR has clear, objective measurement criteria
- **Feasibility Review**: Technical experts assess whether targets are achievable with proposed approach
- **Prioritization Validation**: Stakeholders confirm importance rankings align with business goals
- **Compliance Check**: Legal/compliance experts verify regulatory requirements are correctly interpreted
- **Benchmark Comparison**: Comparing proposed targets against industry standards and competitors
- **Risk Assessment Review**: Ensuring high-risk areas have appropriately stringent requirements
- **Implementation Review**: Designers confirm requirements can be translated into technical solutions

**Refinement Practices**:
- **Ambiguity Resolution**: Replacing vague terms with specific, measurable criteria
- **Granularity Adjustment**: Splitting overly broad requirements or combining redundant ones
- **Context Addition**: Adding environment, stimulus, and response details to create scenarios
- **Measurement Definition**: Specifying exact metrics, tools, methods, and acceptance thresholds
- **Traceability Enhancement**: Linking NFRs to business goals, user needs, and regulatory sources
- **Documentation Improvement**: Ensuring consistent format, numbering, and cross-referencing
- **Validation Planning**: Defining how each NFR will be tested and validated
- **Ownership Assignment**: Clarifying who is responsible for delivering and verifying each NFR
- **Dependency Identification**: Noting when one NFR affects achievement of another (e.g., encryption impacts performance)
- **Version Control**: Tracking changes to NFRs over time with rationale for modifications

## 5. Common Mistakes in Writing Non-Functional Requirements

### Vague or Unmeasurable Language
**Mistake**: Using imprecise terms that prevent objective evaluation
**Examples**:
- "The system should be fast and responsive"
- "The system needs to be highly secure"
- "The system ought to be easy to use"
- "The system must be reliable"
- "The system should scale well"

**Solutions**:
- Replace vague adjectives with measurable criteria: "respond within 2 seconds 95% of time"
- Define what "highly secure" means: specific encryption standards, authentication requirements, etc.
- Specify usability metrics: task completion time, error rates, satisfaction scores
- Quantify reliability: MTBF, uptime percentage, maximum acceptable downtime
- Specify scalability targets: concurrent users, transactions per second, data volume limits
- Reference external standards or benchmarks: "comply with ISO/IEC 25010 performance standards"
- Ask: "How will we objectively measure that this requirement is met?"
- Use units and precise values: milliseconds, megabytes, requests per second, percentages

### Overlooking Important Quality Dimensions
**Mistake**: Focusing only on familiar NFRs while neglecting others that are critical
**Examples**:
- Specifying performance and security but forgetting accessibility or internationalization
- Defining availability requirements but neglecting disaster recovery procedures
- Detailing performance targets but omitting monitoring and alerting needs
- Specifying security controls but forgetting audit logging and compliance reporting
- Defining usability requirements but neglecting learnability and memorability aspects
- Focusing on runtime qualities but ignoring maintainability and technical debt

**Solutions**:
- Use a comprehensive quality attribute framework (like ISO/IEC 25010) as a checklist
- Consider the system's entire lifecycle: development, deployment, operation, maintenance, retirement
- Think about different user types: novice, expert, disabled, international, occasional, frequent
- Consider different operational contexts: normal operation, peak load, failure conditions, maintenance
- Involve specialists: security experts, accessibility consultants, performance engineers
- Review similar systems or industry standards for commonly overlooked qualities
- Ask: "What happens if this quality is poor? Who is affected and how?"
- Create a quality attribute matrix cross-referencing system components with quality dimensions

### Conflicting Non-Functional Requirements
**Mistake**: Two or more NFRs that cannot both be satisfied simultaneously given constraints
**Examples**:
- REQ-PERF-001: "System shall respond to all requests within 100ms"
- REQ-SEC-001: "All data shall be encrypted and decrypted for every request (adding 150ms latency)"
- REQ-AVAIL-001: "System shall achieve 99.999% uptime"
- REQ-MAINT-001: "System shall allow hot code updates without restart"
- REQ-PERF-002: "System shall support real-time video streaming (requires consistent resources)"
- REQ-COST-001: "System shall use commodity hardware to minimize costs"
- REQ-SEC-002: "System shall implement defense-in-depth with multiple security layers"
- REQ-PORT-001: "System shall run on legacy Windows XP systems"

**Solutions**:
- Identify conflicts early through systematic review and analysis
- Use trade-off analysis sessions to explicitly examine competing quality goals
- Look for technical compromises or intermediate solutions that partially satisfy both
- Consider temporal or contextual separation ("during peak hours...", "for premium users...")
- Investigate alternative approaches that might satisfy both requirements differently
- Document trade-off decisions with clear rationale and stakeholder agreement
- Escalate to appropriate decision-makers when conflicts involve fundamental architectural choices
- Consider whether one requirement can be relaxed or phased over time
- Use modeling and simulation to test feasibility of combined requirements

### Ignoring Interdependencies Between Quality Attributes
**Mistake**: Treating each NFR as independent when they often influence each other
**Examples**:
- Strong encryption improves security but typically degrades performance
- Increased redundancy improves availability but increases complexity and cost
- Detailed audit logging improves security and accountability but impacts performance and storage
- Strict input validation improves security but may affect usability and throughput
- Comprehensive monitoring improves operability but adds overhead and complexity
- Localization improves usability for international users but increases complexity and testing burden
- Caching improves performance but can introduce consistency complexities
- Microservices improve scalability and deployability but increase operational complexity and latency

**Solutions**:
- Model quality attribute interactions during architecture and design phases
- Create dependency matrices showing how NFRs influence each other
- Consider combined scenarios that test multiple qualities simultaneously (e.g., secure performance under load)
- Use techniques like "quality attribute workshops" to explore trade-offs explicitly
- Prototype combinations of requirements to measure actual impact
- Consult specialists who understand interdependencies (performance engineers who know security costs)
- Document assumptions about quality interactions in architecture decision records
- Plan for measurement and validation of combined quality scenarios
- Consider ordering of implementation when some qualities affect measurement of others

### Specifying Solutions Instead of Qualities
**Mistake**: Dictating how to achieve a quality rather than stating the quality goal itself
**Examples**:
- "The system shall use Redis caching to achieve fast response times"
- "The system shall deploy to three availability zones for high availability"
- "The system shall implement OAuth 2.0 for secure authentication"
- "The system shall use microservices architecture to achieve scalability"
- "The system shall use AWS WAF for protection against web attacks"
- "The system shall implement CI/CD pipeline for maintainability"

**Solutions**:
- Focus on the quality goal: "The system shall respond to 95% of requests within 2 seconds"
- Let architects and developers decide how to achieve the quality goal
- Specify interface or contract requirements instead of specific implementations: "The system shall provide a caching interface for frequently accessed data"
- State quality requirements in terms of outcomes, not mechanisms
- Consider creating separate "design constraints" document for necessary technical limitations
- Ask: "What quality are we trying to achieve? Why is this specific solution necessary?"
- Involve architects to review for premature design decisions in NFRs
- Use patterns like: "The system shall achieve [quality goal] through [approach category if necessary, e.g., caching, redundancy, encryption]"

### Poor Prioritization of Non-Functional Requirements
**Mistake**: Treating all NFRs as equally critical or failing to distinguish must-haves from nice-to-haves
**Examples**:
- Marking every performance, security, and usability requirement as "must have" for MVP
- Failing to differentiate between baseline acceptability and excellence targets
- Not considering that some qualities may be addressed in later phases or releases
- Over-investing in low-impact qualities while neglecting critical ones
- Not adjusting priorities based on changing business context or technical feasibility

**Solutions**:
- Use established prioritization frameworks (MoSCoW, WSJF, Kano model, etc.) specifically for NFRs
- Differentiate between threshold requirements (must be met) and excellence goals (nice to have)
- Consider business impact: Which NFR deficiencies would cause most harm if not met?
- Consider risk: Which NFR failures pose greatest safety, financial, or reputational risk?
- Consider feasibility: What can realistically be achieved given timeline, budget, and technology constraints?
- Consider dependencies: Some NFRs must be in place before others can be meaningfully addressed
- Review and adjust priorities regularly as understanding evolves and circumstances change
- Involve stakeholders in prioritization to ensure alignment with business goals and user needs
- Consider creating multiple NFR sets for different releases or phases (MVP vs. mature product)

### Inadequate Validation Planning
**Mistake**: Writing NFRs without considering how they will be tested, measured, or validated
**Examples**:
- Specifying performance targets without defining test scenarios, tools, or acceptance procedures
- Stating security requirements without planning for penetration testing or vulnerability scanning
- Defining usability requirements without planning for user testing or accessibility audits
- Specifying availability requirements without defining failure injection or recovery testing
- Detailing maintainability goals without defining code review, testing, or measurement practices
- Stating portability requirements without defining target environments or migration procedures

**Solutions**:
- For each NFR, define how it will be measured and validated before writing the requirement
- Specify test methods, tools, and procedures: "Performance will be measured using JMeter with scenario X"
- Define acceptance criteria that are objectively evaluable: "95% of response times under 2 seconds"
- Consider measurement frequency: continuous monitoring, periodic testing, or pre-release validation
- Identify required instrumentation: logging, metrics collection, profiling, or special test harnesses
- Plan for baseline establishment: measuring current state to understand improvement needed
- Consider production vs. testing environment differences in validation approaches
- Involve testers and quality assurance specialists in NFR definition
- Plan for ongoing validation during development, not just pre-release checks
- Define escalation procedures when NFRs are not met during validation
- Consider third-party validation for critical requirements (security certifications, accessibility audits)

### Ignoring Context and Conditions
**Mistake**: Writing NFRs that don't specify under what conditions they apply
**Examples**:
- "The system shall respond within 2 seconds" (without specifying load, data size, or complexity)
- "The system shall support 10,000 users" (without specifying what those users are doing)
- "The system shall be secure" (without specifying threat model or data sensitivity)
- "The system shall be easy to use" (without specifying user expertise or task complexity)
- "The system shall be available 99.9% of time" (without specifying maintenance windows or measurement period)

**Solutions**:
- Always specify the environment or conditions: "under normal load", "during peak hours", "with datasets up to 10GB"
- Define the specific operations or user actions: "for search requests with up to 5 filters", "when performing account transfers"
- Specify measurement periods: "monthly uptime excluding scheduled maintenance", "average response time over 5-minute windows"
- Define thresholds and boundaries: "for requests under 1MB payload size", "with network latency under 50ms"
- Consider different user types: "for novice users completing core tasks", "for expert users performing advanced operations"
- Specify data characteristics: "with customer records up to 100,000", "when processing images up to 5MB"
- Define failure conditions: "when single node fails", "during network partition between availability zones"
- Specify temporal aspects: "during business hours (8am-6pm local time)", "during holiday shopping season"
- Use quality attribute scenarios to capture context explicitly: source, stimulus, environment, artifact, response, measure

### Lack of Traceability and Rationale
**Mistake**: Writing NFRs without linking them to sources, goals, or justifying their importance
**Examples**:
- NFRs that appear to come from nowhere with no connection to business objectives
- Requirements that seem arbitrarily chosen without explanation of why they matter
- NFRs that contradict stated goals without resolution or trade-off documentation
- Requirements that are copied from templates or previous projects without context consideration
- NFRs that lack justification for the level of stringency chosen

**Solutions**:
- Link each NFR to its source: stakeholder interview, regulatory requirement, industry standard, business goal
- Document the rationale: why this level of quality is needed and what happens if not met
- Trace NFRs forward to design components, architecture decisions, and test plans
- Maintain a rationale or justification field for each requirement explaining its importance
- Consider creating a "goal tree" linking business objectives to quality attributes to specific requirements
- Review NFRs for consistency with architectural principles and constraints
- Document assumptions and dependencies that affect NFR feasibility
- Track changes to NFRs with rationale for modifications (why increased/decreased stringency)
- Involve stakeholders in reviewing whether NFRs accurately reflect their needs and concerns
- Plan for reviewing NFRs during project retrospectives to improve future elicitation

## 6. Practical Exercise: Writing Non-Functional Requirements

### Scenario
You are defining non-functional requirements for an e-commerce platform that handles product catalog browsing, shopping cart management, payment processing, order fulfillment, and customer account management.

### Exercise Part 1: Converting Quality Goals to Specific NFRs
Convert these quality goals into specific, measurable non-functional requirements.

**Quality Goals**:
1. The system should be fast and responsive for customers browsing products
2. The system needs to handle high traffic during holiday sales and promotional events
3. The system must be secure to protect customer payment and personal information
4. The system should be easy to use for customers of varying technical abilities
5. The system must be reliable and available for customers to place orders
6. The system should be easy to maintain and update for the development team
7. The system needs to work across different devices and screen sizes
8. The system should be able to grow as the business expands to new markets and product categories

**Sample Answers**:
1. "The system shall respond to 95% of product catalog browse requests within 1 second under normal load (up to 100 concurrent users)"
2. "The system shall maintain response times under 3 seconds for 90% of requests during peak load of 50,000 concurrent users"
3. "The system shall encrypt all payment card information using AES-256 encryption at rest and TLS 1.3 in transit, complying with PCI DSS Level 1 requirements"
4. "New customers shall be able to complete their first purchase in under 3 minutes without assistance, achieving a System Usability Scale (SUS) score of at least 75"
5. "The system shall achieve 99.95% monthly uptime excluding scheduled maintenance windows (maximum 4 hours per month)"
6. "The system shall maintain at least 80% code coverage with automated unit tests and enable deployment to production within 15 minutes of commit to main branch"
7. "The system shall provide a responsive user interface that adapts to screen widths from 320px (mobile) to 1920px (desktop) without loss of functionality or requiring horizontal scrolling"
8. "The system shall support horizontal scaling to handle increased load by adding identical application instances without code changes or configuration modifications"

### Exercise Part 2: Writing Quality Attribute Scenarios
Write quality attribute scenarios for three of the quality goals above using the six-part format.

**Sample Answers**:
- **Performance Scenario for Product Browsing**:
  - **Source**: External customer
  - **Stimulus**: Requests product category page with 50 items, each showing image, name, price, and brief description
  - **Environment**: Normal operating conditions (up to 500 concurrent users)
  - **Artifact**: Product catalog service and database
  - **Response**: Retrieves product data, renders page, and delivers to customer browser
  - **Response Measure**: 90% of page loads completed within 1.5 seconds; 99% within 3 seconds

- **Security Scenario for Payment Processing**:
  - **Source**: External attacker
  - **Stimulus**: Attempts to intercept network traffic between customer browser and payment gateway
  - **Environment**: Internet-facing production system handling live transactions
  - **Artifact**: Payment processing service and network communication channels
  - **Response**: Prevents successful interception and data theft through encryption
  - **Response Measure**: 0% of sensitive payment data exposed in network traces; all transmissions use TLS 1.3 with perfect forward secrecy

- **Availability Scenario for Order Processing**:
  - **Source**: Internal infrastructure (database cluster)
  - **Stimulus**: Loss of primary database node due to hardware failure
  - **Environment**: Peak shopping period (Black Friday, 20,000 concurrent users)
  - **Artifact**: Order management system and database storage
  - **Response**: Automatically fails over to replica node and continues processing orders
  - **Response Measure**: Failover completes within 10 seconds with zero order loss or duplication; system maintains 99.9% availability during incident

### Exercise Part 3: Identifying Trade-offs Between Non-Functional Requirements
Identify potential trade-offs between pairs of non-functional requirements for this e-commerce system.

**Sample Answers**:
- **Security vs. Performance**:
  - **Trade-off**: Strong encryption (AES-256, TLS 1.3) provides better security but increases computational overhead
  - **Impact**: Encryption/decryption adds latency to every request; SSL/TLS handshake increases connection establishment time
  - **Mitigation Strategies**: Use hardware acceleration for cryptographic operations, implement session resumption, use efficient encryption modes, consider terminating SSL at load balancer with backend encryption

- **Usability vs. Security**:
  - **Trade-off**: Strong authentication requirements (multi-factor, complex passwords) improve security but can frustrate users
  - **Impact**: Additional login steps increase time to complete purchase; complex passwords lead to more reset requests and abandoned carts
  - **Mitigation Strategies**: Implement risk-based authentication (step up only for high-risk actions), offer biometric alternatives, provide password managers integration, use progressive disclosure for security features

- **Availability vs. Maintainability**:
  - **Trade-off**: High availability requirements (zero-downtime deployments, complex failover) increase system complexity
  - **Impact**: More complex deployment procedures increase chance of errors; sophisticated monitoring requires specialized skills to operate
  - **Mitigation Strategies**: Invest in automation and tooling for complex operations, use blue/green or canary deployment patterns, provide thorough operational training, implement comprehensive diagnostics and self-healing capabilities

- **Performance vs. Cost**:
  - **Trade-off**: High performance requirements often necessitate more expensive hardware or complex architectures
  - **Impact**: SSD storage, high-end CPUs, load balancers, and caching infrastructure increase infrastructure costs
  - **Mitigation Strategies**: Use cloud auto-scaling to match resources to demand, implement efficient caching strategies, optimize code and database queries before scaling hardware, consider hybrid approaches with burst capacity

- **Scalability vs. Consistency**:
  - **Trade-off**: Horizontal scaling for performance and availability can challenge data consistency
  - **Impact**: Distributed systems face challenges with ACID transactions; eventual consistency models may show stale data to users
  - **Mitigation Strategies**: Use appropriate consistency models for different data types (strong for financial, eventual for recommendations), implement conflict resolution strategies, use distributed transactions sparingly and with compensation patterns

- **Internationalization vs. Performance**:
  - **Trade-off**: Supporting multiple languages and locales increases complexity and resource usage
  - **Impact**: Larger resource bundles, additional text processing, and potential font loading can impact performance
  - **Mitigation Strategies**: Lazy-load locale resources, use efficient internationalization libraries, optimize text rendering, consider server-side localization for static content

### Exercise Part 4: Creating a Non-Functional Requirements Traceability Matrix
Create a sample traceability matrix linking non-functional requirements to business objectives, user needs, and test procedures.

**Sample Answer**:

| NFR ID | Non-Functional Requirement | Linked Business Objective | Linked User Need/Test Case | Validation Method |
|--------|----------------------------|---------------------------|----------------------------|-------------------|
| NFR-PERF-001 | System shall respond to 95% of product catalog browse requests within 1 second under normal load (up to 100 concurrent users) | Increase conversion rate by reducing bounce due to slow page loads | Users expect fast browsing experience; TC-PERF-001: Measure response times for category page loads under normal load | Load testing with JMeter; measure 95th percentile response time |
| NFR-PERF-002 | System shall maintain response times under 3 seconds for 90% of requests during peak load of 50,000 concurrent users | Capture revenue during high-traffic promotional events without losing customers to frustration | Users abandon carts during slow checkout; TC-PERF-002: Stress test during simulated Black Friday traffic | Stress testing; measure 90th percentile response time under peak load |
| NFR-SEC-001 | System shall encrypt all payment card information using AES-256 encryption at rest and TLS 1.3 in transit, complying with PCI DSS Level 1 requirements | Avoid financial penalties and reputational damage from data breaches | Customers trust their payment information is secure; TC-SEC-001: Verify encryption and transmission security | PCI DSS audit; network traffic analysis; storage encryption verification |
| NFR-SEC-002 | System shall implement multi-factor authentication for administrative access to prevent unauthorized system changes | Reduce risk of compromised admin accounts leading to data breaches or fraud | Administrators need secure access to manage store; TC-SEC-002: Test MFA effectiveness against credential theft | Penetration testing; authentication bypass attempts; login logging verification |
| NFR-USAB-001 | New customers shall be able to complete their first purchase in under 3 minutes without assistance, achieving a System Usability Scale (SUS) score of at least 75 | Increase customer acquisition and reduce abandonment during onboarding | New users find purchase process confusing; TC-USAB-001: Measure task completion time and satisfaction | Usability testing with first-time users; SUS questionnaire; task timing |
| NFR-AVAIL-001 | System shall achieve 99.95% monthly uptime excluding scheduled maintenance windows (maximum 4 hours per month) | Maintain revenue stream and customer trust through consistent availability | Customers expect to shop whenever they want; TC-AVAIL-001: Measure availability over month with failure injection | Production monitoring; chaos engineering; failover testing; SLA reporting |
| NFR-MAINT-001 | System shall maintain at least 80% code coverage with automated unit tests and enable deployment to production within 15 minutes of commit to main branch | Reduce defects and increase release frequency to respond to market changes | Developers need confidence in changes; TC-MAINT-001: Measure test coverage and deployment pipeline speed | Code coverage reports; deployment pipeline timing; release frequency metrics |
| NFR-PORT-001 | System shall provide a responsive user interface that adapts to screen widths from 320px (mobile) to 1920px (desktop) without loss of functionality or requiring horizontal scrolling | Reach customers across different devices and contexts | Mobile users need usable interface; TC-PORT-001: Test layout and functionality across device sizes | Responsive design testing; manual verification on devices; automated visual regression testing |
| NFR-SCALE-001 | System shall support horizontal scaling to handle increased load by adding identical application instances without code changes or configuration modifications | Support business growth without major rearchitecture for each expansion phase | System becomes slow during growth periods; TC-SCALE-001: Measure performance improvement with added instances | Load testing with increasing instance counts; performance metrics; resource utilization monitoring |

## 7. Checklist for Evaluating Non-Functional Requirements

Use this checklist to assess whether your non-functional requirements meet quality standards:

### Basic Structure and Format
- [ ] Each requirement has a unique, persistent identifier
- [ ] Requirement uses appropriate language for NFRs (may use "shall" for mandatory, "should" for desired)
- [ ] Requirement is formatted consistently with other NFRs
- [ ] Requirement clearly identifies which quality attribute it addresses (performance, security, etc.)
- [ ] Requirement specifies measurable criteria where applicable
- [ ] Requirement avoids design or solution specification unless absolutely necessary
- [ ] Requirement is written in present tense, not future tense
- [ ] Requirement is free of spelling, grammar, and punctuation errors
- [ ] Requirement avoids marketing language, hype, or subjective statements
- [ ] Requirement focuses on need, not wish_list or nice_to_have
- [ ] Requirement specifies necessary conditions, environment, or assumptions where relevant
- [ ] Requirement identifies stimulus or trigger where applicable (especially in scenario format)
- [ ] Requirement describes expected response or behavior
- [ ] Requirement specifies how the response will be measured or evaluated

### Content and Clarity
- [ ] Requirement expresses a single, coherent quality attribute or constraint
- [ ] Requirement is understandable to intended audience (technical vs business)
- [ ] Requirement does not contain ambiguous or vague terms
- [ ] All acronyms, abbreviations, and specialized terms are defined
- [ ] Requirement specifies measurable outcomes where applicable (response time, throughput, percentage, etc.)
- [ ] Requirement includes necessary preconditions and assumptions
- [ ] Requirement addresses both normal operation and relevant stress/failure conditions
- [ ] Requirement is feasible to implement with available resources and technology
- [ ] Requirement is necessary to meeting stakeholder needs or business objectives
- [ ] Requirement does not duplicate or overlap unnecessarily with other requirements
- [ ] Requirement considers relevant regulatory, standards, or compliance requirements
- [ ] Requirement addresses both positive scenarios and relevant error/exception conditions

### Completeness and Specificity
- [ ] Requirement specifies the source of stimulus (who/what triggers the quality evaluation)
- [ ] Requirement specifies the environmental conditions under which it applies
- [ ] Requirement specifies the artifact or system component being evaluated
- [ ] Requirement specifies the response or behavior expected from the system
- [ ] Requirement specifies the response measure or evaluation criteria
- [ ] Requirement specifies acceptable ranges, limits, or thresholds where applicable
- [ ] Requirement specifies data formats, units, precision, and formatting where relevant
- [ ] Requirement specifies sequencing or ordering requirements where relevant
- [ ] Requirement specifies handling of edge cases, boundaries, and exceptions
- [ ] Requirement specifies any necessary cleanup, rollback, or recovery actions
- [ ] Requirement specifies notification or alerting requirements where appropriate
- [ ] Requirement specifies timing, frequency, or duration requirements where applicable
- [ ] Requirement specifies resource utilization constraints where applicable (memory, CPU, storage, bandwidth)
- [ ] Requirement specifies geographical or deployment constraints where applicable
- [ ] Requirement specifies temporal validity (e.g., applies during peak season only, expires after date)

### Traceability and Alignment
- [ ] Requirement can be traced to a legitimate source (stakeholder interview, document, regulation, goal)
- [ ] Requirement supports forward traceability to architecture decisions or design components
- [ ] Requirement supports forward traceability to test procedures or validation methods
- [ ] Requirement aligns with stated business objectives or user needs
- [ ] Requirement does not contradict any other requirement in the set
- [ ] Requirement uses consistent terminology with glossary and other requirements
- [ ] Requirement is at appropriate level of detail for current phase of development
- [ ] Requirement does not prematurely specify implementation or design decisions
- [ ] Requirement includes rationale or justification where helpful for understanding
- [ ] Requirement indicates priority or importance level where relevant
- [ ] Requirement considers synergistic or conflicting relationships with other quality attributes

### Testability and Validation
- [ ] Requirement includes clear, measurable acceptance criteria
- [ ] Acceptance criteria are objectively evaluable (not based on opinion or interpretation)
- [ ] Requirement can be validated through inspection, analysis, demonstration, or testing
- [ ] Test cases can be readily derived from acceptance criteria
- [ ] Acceptance criteria specify tools, methods, or standards to be used for evaluation
- [ ] Requirement specifies conditions under which it must be met (environment, load, etc.)
- [ ] Requirement distinguishes between mandatory behavior and optional features
- [ ] Acceptance criteria are feasible to validate within project constraints (time, budget, etc.)
- [ ] Requirement supports both positive testing (normal conditions) and negative testing (stress/failure conditions)
- [ ] Requirement specifies expected behavior for error conditions and exception handling
- [ ] Acceptance criteria specify timing or frequency requirements where applicable
- [ ] Requirement specifies calibration or baseline requirements where applicable (establishing current state)
- [ ] Requirement specifies comparison criteria where applicable (better than current system, industry benchmark)
- [ ] Acceptance criteria specify statistical requirements where applicable (percentiles, averages, confidence intervals)
- [ ] Requirement specifies validation frequency where applicable (continuous monitoring, periodic testing, pre-release)

### Professional Quality
- [ ] Requirement contributes to clear, organized NFR set
- [ ] Similar requirements are structured consistently for ease of comparison
- [ ] Requirement has been reviewed by relevant stakeholders for accuracy
- [ ] Requirement has been validated with end users where applicable (usability, accessibility)
- [ ] Requirement has been examined for consistency with related requirements
- [ ] Requirement has been checked for feasibility with technical experts
- [ ] Requirement has been assessed for usability implications where relevant
- [ ] Requirement has been evaluated for security and privacy implications where relevant
- [ ] Requirement has been reviewed for regulatory and compliance implications where appropriate
- [ ] Requirement shows evidence of iterative refinement based on feedback
- [ ] Requirement is appropriate for inclusion in NFR baseline
- [ ] Requirement definition of done criteria have been met for this requirement

## 8. Definition of Done for Non-Functional Requirements

Non-functional requirements for a specific increment, release, or iteration are considered complete when:

### Elicitation and Collection
- [ ] All relevant stakeholder groups have been consulted using appropriate methods for quality attribute discovery
- [ ] New stakeholders discovered during the process (performance engineers, security experts, accessibility consultants) have been identified and engaged
- [ ] Relevant documents, standards, regulations, and benchmark data have been examined for NFRs
- [ ] Regulatory and compliance requirements impacting NFRs have been identified and documented
- [ ] Functional requirements have been reviewed to derive implied NFRs (performance, security, usability implications)
- [ ] User goals, tasks, and scenarios have been explored to derive quality attribute needs
- [ ] Pain points, workarounds, and undesirable behaviors related to system qualities have been identified
- [ ] Desired quality levels and benefits have been clarified from stakeholder perspective
- [ ] Assumptions, constraints, and dependencies have been documented and validated
- [ ] Open questions and uncertainties have been recorded with owners and target resolution dates
- [ ] Different usage contexts (normal, peak, failure, maintenance) have been considered for each quality attribute
- [ ] Both positive aspirations and protective requirements (security, reliability) have been elicited

### Analysis and Specification
- [ ] NFRs have been analyzed for completeness, consistency, and feasibility using quality attribute frameworks
- [ ] Conflicting NFRs have been identified, discussed, and resolved with documented decisions
- [ ] Ambiguous, vague, or unclear NFRs have been clarified using quality attribute scenarios or measurable criteria
- [ ] Redundant or duplicative NFRs have been identified and eliminated
- [ ] NFRs have been specified using appropriate formats (scenarios, measurable statements, etc.) for intended audiences
- [ ] Each NFR has a unique, persistent identifier that survives text changes
- [ ] Acceptance criteria have been defined for each NFR with clear measurement procedures
- [ ] NFRs have been prioritized using agreed-upon method and criteria (considering business impact, risk, feasibility)
- [ ] Glossary of domain-specific terms related to quality attributes is complete and reviewed by subject matter experts
- [ ] NFRs are organized logically by quality attribute category for easy navigation, reference, and understanding
- [ ] Architecture diagrams, models, or visual representations have been created where beneficial for understanding NFR implications
- [ ] NFRs have been allocated to appropriate components, subsystems, or services where applicable
- [ ] Data flow, interface, and resource requirements have been specified where relevant to NFRs
- [ ] State transition and behavior requirements have been specified for NFRs affecting system dynamics
- [ ] Error handling and exception requirements have been specified for all major functions affecting NFRs
- [ ] Input validation, output requirements, and resource constraints have been specified where relevant to NFRs
- [ ] Timing, frequency, sequencing, and scalability requirements have been specified where needed for NFRs
- [ ] Localization, internationalization, and portability requirements have been identified where applicable
- [ ] Accessibility and usability requirements have been considered for all user-facing functions
- [ ] Security and privacy requirements have been identified where functions handle sensitive data
- [ ] Performance and throughput requirements have been identified where response speed matters
- [ ] Maintenance, support, and operational requirements have been identified where applicable
- [ ] NFRs have been checked for feasibility with architects, performance engineers, and security specialists
- [ ] NFRs have been assessed for testability and validation approaches with QA and testing specialists
- [ ] NFRs have been reviewed for potential technical debt or maintenance implications
- [ ] Lessons learned from the NFR process have been documented for future improvement
- [ ] NFRs have been evaluated for their impact on architectural decisions and constraints
- [ ] Potential needle-in-haystack problems (rare but severe quality failures) have been considered
- [ ] Long-term evolution and technical debt accumulation have been considered for maintainability NFRs
- [ ] NFRs have been assessed for their impact on development velocity and release frequency
- [ ] NFRs have been reviewed for their effect on operational complexity and support requirements
- [ ] NFRs have been checked for their influence on total cost of ownership and return on investment
- [ ] NFRs have been examined for their effect on user satisfaction, loyalty, and brand perception
- [ ] NFRs have been considered in relation to competitive differentiation and market positioning
- [ ] Definition of done criteria have been met for the NFR set as a whole
- [ ] Plan exists for ongoing NFR refinement during development phases
- [ ] Stakeholders understand which NFRs are in vs. out of current scope/release
- [ ] Estimates of effort, complexity, and risk have been assigned to NFRs where appropriate
- [ ] Dependencies between NFRs have been identified, documented, and managed
- [ ] NFRs have been reviewed for potential user experience and accessibility issues
- [ ] NFRs have been evaluated for alignment with architectural principles and constraints
- [ ] NFRs have been checked for legal and regulatory compliance where applicable
- [ ] NFRs have been assessed for potential security and privacy implications where handling sensitive data
- [ ] NFRs have been examined for performance characteristics and scalability implications
- [ ] NFRs have been reviewed for maintainability and technical debt considerations
- [ ] NFRs have been validated for consistency with organizational standards and policies
- [ ] Definition of done for each individual NFR has been met according to the checklist above

### Validation and Agreement
- [ ] NFRs have been reviewed with stakeholders for accuracy and completeness
- [ ] NFRs have been validated with end users where applicable through multiple techniques (usability testing, accessibility audits)
- [ ] Performance NFRs have been validated with load testing, stress testing, and benchmarking
- [ ] Security NFRs have been validated with penetration testing, vulnerability scanning, and code review
- [ ] Availability NFRs have been validated with failure injection, chaos engineering, and recovery testing
- [ ] Usability NFRs have been validated with user testing, heuristic evaluation, and accessibility testing
- [ ] Maintainability NFRs have been validated with code analysis, test coverage measurement, and build/deployment timing
- [ ] Portability NFRs have been validated with cross-platform testing and migration exercises
- [ ] Regulatory and compliance NFRs have been validated with appropriate specialists and audit preparation
- [ ] NFRs have been assessed for clarity and understandability by intended audience
- [ ] NFRs baseline has been established, documented, and communicated
- [ ] Formal agreement or sign-off has been obtained from key stakeholder representatives
- [ ] Change control process has been defined, documented, and agreed upon
- [ ] Traceability links have been established between NFRs and their sources
- [ ] Work has begun on establishing forward traceability to design concepts
- [ ] Testability of NFRs has been assessed and confirmed as feasible
- [ ] Definition of done criteria have been met for the NFR set as a whole
- [ ] Plan exists for ongoing NFR refinement during development phases
- [ ] Stakeholders understand which NFRs are in vs. out of current scope/release
- [ ] Estimates of effort, complexity, and risk have been assigned to NFRs where appropriate
- [ ] Dependencies between NFRs have been identified, documented, and managed
- [ ] NFRs have been reviewed for potential user experience and accessibility issues
- [ ] NFRs have been evaluated for alignment with architectural principles and constraints
- [ ] NFRs have been checked for legal and regulatory compliance where applicable
- [ ] NFRs have been assessed for potential security and privacy implications where handling sensitive data
- [ ] NFRs have been examined for performance characteristics and scalability implications
- [ ] NFRs have been reviewed for maintainability and technical debt considerations
- [ ] NFRs have been validated for consistency with organizational standards and policies
- [ ] Definition of done for each individual NFR has been met according to the checklist above

## 9. Related Topics

- [[01-REQUIREMENTS-OVERVIEW|01 — Requirements Overview]]: Foundational concepts about requirements engineering
- [[02-FUNCTIONAL-REQUIREMENTS|02 — Functional Requirements]]: What the system should do (features, behaviors, capabilities)
- [[04-TECHNICAL-REQUIREMENTS|04 — Technical Requirements]]: Specific technology, architecture, and implementation constraints
- [[05-SECURITY-REQUIREMENTS|05 — Security Requirements]]: Protection mechanisms for data, systems, and users (often overlaps with NFRs)
- [[08-ARCHITECTURE|08 — Architecture]]: How non-functional requirements drive architectural decisions and patterns
- [[09-DESIGN|09 — Design]]: Detailed specification of how the system will fulfill both functional and non-functional requirements
- [[10-IMPLEMENTATION|10 — Implementation]]: Building the system to satisfy non-functional requirements (performance optimizations, security implementations)
- [[11-TESTING|11 — Testing]]: Verifying that the system correctly implements non-functional requirements (load testing, security testing, usability testing)
- [[12-DEPLOYMENT|12 — Deployment]]: Releasing the system that implements non-functional requirements to users
- [[02-PROBLEM-DEFINITION|02 — Problem Definition]]: Understanding the problem space informs quality attribute needs
- [[03-BUSINESS-UNDERSTANDING|03 — Business Understanding]]: Business goals and value context for non-functional requirement prioritization
- [[04-STAKEHOLDERS|04 — Stakeholders]]: Identifying who cares about which non-functional requirements
- [[05-USER-RESEARCH|05 — User Research]]: Direct insights from users that inform usability and experience requirements
- [[06-USER-PERSONAS|06 — User Personas]]: Framing non-functional requirements from specific user perspectives (accessibility, internationalization)
- [[07-REQUIREMENTS|07 — Requirements]]: The parent phase that encompasses all requirement types
- [[47-SENIOR-ENGINEERING-AND-RETROSPECTIVE|47 — SENIOR ENGINEERING AND RETROSPECTIVE]]: Lessons learned from non-functional requirements processes inform future improvements