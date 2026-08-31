# 06-REVIEW-COMMENTS

## 1. What Are Effective Review Comments?

Effective review comments are specific, actionable, and respectful feedback provided during code review that help improve code quality while maintaining a positive team dynamic. They go beyond simple approval or rejection to provide meaningful insights that help authors learn, improve, and produce better code.

Effective comments balance honesty with empathy, focus on the code rather than the author, and provide clear guidance on what needs to change and why. They serve as teaching moments, knowledge sharing opportunities, and quality improvement mechanisms.

## 2. Why Do Review Comments Matter?

Review comments matter because:

- **Knowledge Transfer**: Comments educate authors about best practices, patterns, and team standards
- **Quality Improvement**: Specific feedback leads to concrete code improvements
- **Consistency**: Help maintain uniform standards across the codebase
- **Mentoring**: Junior developers learn from senior feedback; seniors gain fresh perspectives
- **Documentation**: Comments often contain valuable context and rationale
- **Psychological Safety**: Respectful comments build trust and encourage participation
- **Efficiency**: Clear feedback reduces back-and-forth and speeds up the review process
- **Team Alignment**: Help establish shared understanding of what constitutes good code
- **Learning Opportunities**: Both reviewers and authors learn from the exchange
- **Prevention**: Good comments prevent future issues by teaching rather than just fixing
- **Ownership**: Encourage authors to take responsibility for code quality
- **Continuous Improvement**: Review insights can inform team practices and tooling

## 3. What Problems Do Poor Review Comments Cause?

Poor review comments lead to numerous issues:

- **Defensiveness**: Authors become defensive and less receptive to feedback
- **Confusion**: Vague or unclear comments leave authors unsure what to do
- **Demotivation**: Harsh or dismissive comments reduce enthusiasm and engagement
- **Misalignment**: Authors make incorrect changes due to misunderstood feedback
- **Inefficiency**: Back-and-forth clarifications waste time
- **Knowledge Hoarding**: Critical insights aren't shared effectively
- **Inconsistency**: Different reviewers give conflicting feedback
- **Missed Opportunities**: Valuable teaching moments are lost
- **Erosion of Trust**: Poorly delivered feedback damages working relationships
- **Surface-level Compliance**: Authors make minimal changes just to get approval
- **Frustration**: Both reviewers and authors become frustrated with the process
- **Avoidance Behaviors**: Team members avoid reviewing or having their code reviewed
- **Lost Context**: Rationales and trade-offs aren't preserved
- **Inaction**: Unclear comments result in no changes being made
- **Overwhelm**: Too many nitpicky comments obscure important issues
- **Bias Reinforcement**: Subjective feedback reinforces personal preferences over team standards
- **Context Collapse**: Feedback loses meaning when separated from the code
- **Rationality Questions**: Authors question whether feedback is based on facts or opinions

## 4. Key Dimensions of Effective Review Comments

### 4.1 Specificity and Actionability
- **Concrete Examples**: Point to specific lines or patterns rather than general impressions
- **Clear Instructions**: Tell authors exactly what to change or consider
- **Alternative Suggestions**: Provide specific alternatives when suggesting changes
- **Before/After Contrast**: Show what the code looks like now vs. what it could be
- **Measurable Outcomes**: Link changes to specific quality improvements
- **Reproducible Issues**: Ensure the problem can be consistently identified
- **Scope Definition**: Clearly define what needs to be examined
- **Traceability**: Make it easy for authors to locate and verify the issue
- **Reversibility**: Allow authors to understand what would constitute resolution
- **Prioritization**: Distinguish between must-fix, should-fix, and nice-to-have items

### 4.2 Tone and Delivery
- **Respectful Language**: Treat authors as colleagues deserving of respect
- **Growth Mindset**: Frame feedback as opportunities to learn and improve
- **Blame-Free**: Focus on the code, not perceived shortcomings of the author
- **Appreciative**: Acknowledge what was done well alongside areas for improvement
- **Empathetic**: Consider the author's experience level and context
- **Constructive**: Frame everything in terms of how to make things better
- **Professional**: Maintain workplace-appropriate language and demeanor
- **Encouraging**: Motivate rather than discourage continued effort
- **Humble**: Acknowledge that reviewers can also be mistaken or missing context
- **Grammar-aware**: Pay attention to how wording affects tone

### 4.3 Context Awareness
- **Understanding Intent**: Consider what the author was trying to accomplish
- **Awareness of Constraints**: Recognize time, resource, or technical limitations
- **Knowledge of History**: Understand legacy decisions or technical debt
- **Recognition of Trade-offs**: Acknowledge when compromises were necessary
- **Familiarity with Codebase**: Understand surrounding patterns and conventions
- **Sensitivity to Experience Level**: Adjust feedback depth based on author's background
- **Awareness of Current Workload**: Consider what else the author is working on
- **Understanding of Team Norms**: Respect established practices and conventions
- **Recognition of Experimental Code**: Distinguish between prototype and production code
- **Sensitivity to Frustration Points**: Be aware of known pain points in the codebase

### 4.4 Focus and Relevance
- **Importance Hierarchy**: Focus on significant issues rather than trivialities
- **Change Relevance**: Ensure feedback pertains to the actual change being reviewed
- **Pattern Recognition**: Address recurring issues rather than one-off instances
- **Risk-based Prioritization**: Focus on areas with highest potential impact
- **Efficiency Consideration**: Balance feedback depth with review urgency
- **Learning Value**: Prioritize feedback that teaches broadly applicable concepts
- **Avoiding Bike-shedding**: Don't disproportionately focus on trivial details
- **Maintaining Perspective**: Keep sight of overall goals amidst details
- **Avoiding Nitpicking**: Resist the urge to comment on every possible improvement
- **Strategic Thinking**: Consider how feedback affects long-term maintainability

### 4.5 Educational Value
- **Teaching Moments**: Use comments to explain why certain approaches are preferred
- **Pattern Instruction**: Teach recurring patterns and anti-patterns
- **Principle Explanation**: Connect feedback to underlying software engineering principles
- **Resource Sharing**: Link to documentation, articles, or examples
- **Question Framing**: Use questions to stimulate thinking rather than just declaring
- **Alternative Exploration**: Show different approaches and their trade-offs
- **Concept Clarification**: Help authors understand confusing concepts or terminology
- **Best Practice Highlighting**: Point to examples of good practices in the codebase
- **Mentoring Oppor tunities**: Identify chances to guide professional development
- **Knowledge Connection**: Link feedback to existing team knowledge or training

### 4.6 Timing and Frequency
- **Timeliness**: Provide feedback while the change is fresh in everyone's mind
- **Appropriate Depth**: Match feedback thoroughness to change importance and size
- **Batch Similar Issues**: Group related feedback to reduce noise
- **Single-pass Preference**: Aim to catch most issues in one review cycle
- **Follow-up Opportunities**: Allow for clarification rounds when needed
- **Review Cadence**: Match feedback volume to team review frequency
- **Context Setting**: Provide initial overview before diving into details
- **Summary Statements**: Offer high-level impressions alongside specific comments
- **Positive Reinforcement**: Acknowledge good practices to encourage repetition
- **Closure Signaling**: Clearly indicate when review is complete

## 5. Junior vs Senior Perspective on Review Comments

### Junior Reviewer Tendencies
- **Over-focus on Style**: Excessive attention to formatting and minor syntax
- **Personal Preferences**: Imposing individual tastes as universal standards
- **Literal Interpretation**: Taking requirements exactly as stated without considering intent
- **Missing Context**: Failing to understand why certain approaches were chosen
- **Inconsistent Tone**: Alternating between overly harsh and excessively apologetic
- **Vague Feedback**: Saying "this is confusing" without explaining why
- **Overwhelming Volume**: Providing too many comments making it hard to prioritize
- **Missing Positivity**: Focusing only on what's wrong without acknowledging what's right
- **Inconsistent Standards**: Applying different criteria to different parts of the code
- **Missing Alternatives**: Identifying problems without suggesting solutions
- **Over-reliance on Tools**: Letting linter comments dominate without adding value
- **Fear of Conflict**: Avoiding necessary but potentially uncomfortable feedback

### Senior Reviewer Tendencies
- **Strategic Focus**: Concentrating on architectural, maintainability, and scalability aspects
- **Context Integration**: Understanding business requirements and technical constraints
- **Pattern Recognition**: Spotting recurring issues that indicate systemic problems
- **Teaching Orientation**: Using comments as opportunities to mentor and educate
- **Balanced Feedback**: Mixing praise with constructive criticism appropriately
- **Alternative Thinking**: Considering multiple approaches and their trade-offs
- **Measurement Awareness**: Understanding performance and resource implications
- **Mental Modeling**: Building clear mental models of how the code works
- **Diplomatic Delivery**: Providing tough feedback in ways that are well-received
- **Trend Spotting**: Identifying emerging issues before they become serious problems
- **Knowledge Sharing**: Distributing expertise and institutional knowledge
- **Process Improvement**: Using review insights to suggest team or process enhancements
- **Mental Flexibility**: Being open to different valid approaches
- **Efficiency Consciousness**: Respecting everyone's time while maintaining quality
- **Ownership Promotion**: Encouraging authors to take pride in their work

## 6. Effective Review Comment Checklist

### Before Commenting
- [ ] Have I understood what the code is trying to accomplish?
- [ ] Have I reviewed the associated ticket, design documents, and context?
- [ ] Am I commenting on the code itself, not making assumptions about the author?
- [ ] Have I considered the author's likely experience level?
- [ ] Am I aware of any time pressures or constraints affecting this change?
- [ ] Have I looked for what's done well alongside areas for improvement?
- [ ] Have I checked whether similar issues exist elsewhere I should mention?
- [ ] Am I prepared to explain why I'm suggesting a particular change?
- [ ] Have I considered whether this is the right forum for this discussion?
- [ ] Do I have specific examples or alternatives to share when suggesting changes?

### Comment Content
- [ ] Is my comment specific enough that the author knows exactly what I mean?
- [ ] Does my comment suggest a clear action or alternative when criticism is offered?
- [ ] Is my tone respectful and conducive to a positive response?
- [ ] Have I avoided personalizing feedback or making it about the author?
- [ ] Is my comment focused on important issues rather than trivialities?
- [ ] Does my comment explain why the issue matters (maintainability, security, etc.)?
- [ ] Have I avoided using absolute language like "always" or "never" without justification?
- [ ] Have I considered whether my feedback represents team consensus or personal preference?
- [ ] Is my comment actionable, or does it leave the author guessing what to do?
- [ ] Have I checked whether similar comments could be batched for efficiency?

### Comment Delivery
- [ ] Is my comment concise enough to be easily understood?
- [ ] Have I avoided excessive jargon or unexplained acronyms?
- [ ] Is my comment placed near the relevant code for easy reference?
- [ ] Have I avoided commenting on every single instance of a pattern when a summary would suffice?
- [ ] Is my comment timely relative to when the change was submitted?
- [ ] Have I considered whether this needs synchronous discussion rather than written comments?
- [ ] Have I checked my comment for unintended tone issues before submitting?
- [ ] Am I prepared to clarify or discuss this comment if the author has questions?
- [ ] Have I considered the cumulative effect of all my comments on this review?
- [ ] Would I be comfortable receiving this comment myself?

### After Commenting
- [ ] Have I left room for the author to explain their reasoning or constraints?
- [ ] Am I open to learning that my suggestion isn't feasible or optimal?
- [ ] Have I made it clear that I'm available for follow-up discussion?
- [ ] Have I considered whether I need to retract or modify any comments based on author response?
- [ ] Have I thanked the author for their work and openness to feedback?
- [ ] Have I noted any positive aspects or good practices I observed?
- [ ] Have I considered whether this review revealed patterns worth sharing with the team?
- [ ] Have I made note of anything I learned from reviewing this change?
- [ ] Am I prepared to help implement any agreed-upon changes if needed?
- [ ] Have I considered whether this feedback should inform team practices or tooling?

## 7. Types of Review Comments

### 7.1 Questions and Clarifications
**Purpose**: Seek to understand intent, constraints, or unclear aspects before passing judgment
**When to Use**: When you're uncertain about why something was done a certain way
**Examples**:
- "Can you help me understand why you chose this approach over the alternative we discussed in the last sprint?"
- "I'm not sure I follow the reasoning behind this conditional - could you walk me through the edge cases you're handling here?"
- "What led to the decision to implement this as a synchronous operation rather than using the event queue?"
- "Are there performance considerations I should be aware of with this approach?"

**Effective Pattern**: "I'm curious about [specific aspect]. Could you explain [what you want to understand]?"

### 7.2 Suggestions and Alternatives
**Purpose**: Offer specific ideas for improvement while respecting author autonomy
**When to Use**: When you see a clear opportunity for improvement that maintains functionality
**Examples**:
- "Consider extracting this validation logic into a reusable function since it's used in three places in this file."
- "What do you think about using a map lookup instead of this switch statement for better scalability?"
- "This would be more readable if we renamed 'tmp' to something that indicates its purpose like 'processedResults'."
- "Have you considered using the built-in library function for this instead of implementing it manually?"

**Effective Pattern**: "Have you considered [alternative approach]? It might [benefit] because [reasoning]."

### 7.3 Observations and Concerns
**Purpose**: Point out potential issues, risks, or areas needing attention
**When to Use**: When you notice something that could lead to problems now or in the future
**Examples**:
- "This approach could lead to a N+1 query problem as the user base grows - what are your thoughts on prefetching the related data?"
- "I notice this function doesn't handle null inputs - is that intentional given how it's called?"
- "The error message here might be too technical for end users - could we make it more user-friendly?"
- "This loop doesn't have an upper bound - what prevents it from running indefinitely under adverse conditions?"

**Effective Pattern**: "I noticed [specific observation]. This could lead to [potential issue] because [reasoning]."

### 7.4 Praise and Recognition
**Purpose**: Reinforce good practices and encourage their continuation
**When to Use**: When you see something particularly well-done worth highlighting
**Examples**:
- "This is a really clean implementation of the state machine pattern - easy to follow and extend."
- "Great job handling all the edge cases in this validation function - comprehensive and readable."
- "I appreciate how you've documented the non-obvious business rules in the comments here."
- "The test coverage for this new feature is excellent - you've thought through all the branches."

**Effective Pattern**: "I really appreciated [specific thing] because [why it's good]."

### 7.5 Resources and References
**Purpose**: Share helpful information that authors might not be aware of
**When to Use**: When you know of relevant documentation, examples, or best practices
**Examples**:
- "Our team's performance guide has a section on efficient collection processing that might be helpful here."
- "You might find the example in src/utils/formatters.js useful for how we handle internationalization."
- "The security team recently updated our guidelines on password reset tokens - see CONFLUENCE_LINK."
- "This pattern is similar to how we handled the user preferences migration last quarter - see PR #1234."

**Effective Pattern**: "For reference, [resource] shows [relevant information] that might be helpful here."

### 7.6 Process and Workflow Comments
**Purpose**: Address review process, timing, or workflow aspects
**When to Use**: When you notice something about how the change was prepared or submitted
**Examples**:
- "It would help reviewers if you could break this large change into smaller, logically independent PRs."
- "Adding a brief summary of the business problem this solves would help contextualize the technical changes."
- "Consider updating the related documentation in docs/api.md alongside this code change."
- "The commit messages could be more descriptive - consider following our conventional commits guidelines."

**Effective Pattern**: "To help with [process aspect], consider [suggestion] because [benefit]."

## 8. Real-World Examples

### Example 1: Specific and Actionable Feedback
**Less Effective**: "This function is confusing and needs to be cleaner."
**More Effective**: "In the `calculateDiscount` function on lines 45-62, the nested conditionals make it hard to follow the discount logic. Consider extracting each discount tier into a separate private method like `applySeniorDiscount(amount)` and `applyVolumeDiscount(amount, quantity)`. This would make the main function read like a sequence of clear steps rather than a complex decision tree."

**Why it's better**:
- Specific location identified (lines 45-62 in calculateDiscount)
- Clear explanation of what's confusing (nested conditionals)
- Specific suggestion (extract to private methods)
- Examples of what the methods could be named
- Explanation of benefit (reads like clear sequence of steps)
- Actionable and concrete

### Example 2: Respectful and Educational Tone
**Less Effective**: "You shouldn't be using raw SQL queries here - everyone knows to use the ORM."
**More Effective**: "I notice we're using raw SQL in the `getUserOrders` method on line 78. While this works, our team generally prefers using the ORM for database queries because it provides better protection against SQL injection and makes queries more portable across database systems. Would you be open to rewriting this using the UserRepository.findBy() methods we use elsewhere in the codebase?"

**Why it's better**:
- Specific location identified (line 78 in getUserOrders)
- Explains the concern (SQL injection risk, portability)
- References team practice (general preference for ORM)
- Explains why the practice exists (protection, portability)
- Asks rather than demands ("Would you be open to...")
- References existing code for guidance (UserRepository.findBy methods)
- Maintains respectful tone throughout

### Example 3: Context-aware Feedback
**Less Effective**: "Why did you use a synchronous approach here? This will block the thread and cause performance issues."
**More Effective**: "I see you've implemented the file processing synchronously in the `importData` method. Given that this runs during user uploads and we're seeing larger files lately, I'm concerned about thread blocking under load. Looking at the ticket, it mentions this should handle files up to 10MB - could we consider making this asynchronous using the background job queue we use for similar operations? If there are reasons it needs to be synchronous (like transactional requirements or immediate feedback needs), could we document those constraints?"

**Why it's better**:
- Shows understanding of the code (synchronous file processing in importData)
- Connects to observable issue (larger files, thread blocking)
- References relevant context (ticket mentioning 10MB file size)
- Suggests specific alternative (background job queue)
- Acknowledges potential constraints (transactional requirements, feedback needs)
- Asks for documentation rather than assuming oversight
- Focuses on problem-solving rather than blame

### Example 4: Balanced Feedback
**Less Effective**: "This whole approach is wrong. You need to start over."
**More Effective**: "I appreciate how you've handled the error cases in this validation logic - it's comprehensive and readable. For the core algorithm on lines 90-110, I'm wondering if we could simplify it by using the existing `DataTransformer` utility class we created last month. It already handles the case conversion and trimming we're doing here, and would reduce duplication. The validation portion looks great though - clear and thorough."

**Why it's better**:
- Starts with specific praise (error handling is comprehensive and readable)
- Identifies specific area for improvement (core algorithm lines 90-110)
- Makes specific suggestion (use existing DataTransformer class)
- Explains benefit (reduce duplication, reuse existing code)
- Acknowledges what's working well (validation portion looks great)
- Maintains balanced perspective throughout
- Shows awareness of existing codebase resources

### Example 5: Educational and Strategic Feedback
**Less Effective**: "Don't use loops like this - it's inefficient."
**More Effective**: "In the `processItems` method, I notice we're iterating through the entire collection to find matching items on lines 132-145. Given that we're doing this lookup frequently and the collection can grow large, this O(n) search could become a performance bottleneck. Have you considered using a Map or Set indexed by the lookup key instead? This would give us O(1) lookups and scale much better as our data grows. The team's performance guide section 4.2 has examples of this pattern if you'd like to reference it."

**Why it's better**:
- Specific location identified (processItems method, lines 132-145)
- Explains the inefficiency (O(n) search becoming bottleneck)
- Connects to observable context (frequent lookup, growing collection)
- Suggests specific alternative (Map or Set for O(1) lookups)
- Explains benefit (scales better as data grows)
- Provides reference for learning (performance guide section 4.2)
- Focuses on teaching rather than just criticizing
- Shows awareness of team resources

## 9. Comment Templates for Common Scenarios

### When Suggesting Refactoring
"I noticed [specific code pattern] in [location]. This could benefit from [refactoring technique] because [reasoning]. For example, we could [specific suggestion] which would [benefit]. Have you considered this approach, or are there constraints I'm missing?"

### When Pointing Out Potential Bugs
"In [location], I see [specific observation]. This might lead to [potential problem] under [conditions]. Could we consider [alternative approach] to handle this case? What do you think about [specific suggestion]?"

### When Asking for Clarification
"Help me understand [specific aspect] - I'm not sure I follow the reasoning behind [what you're curious about]. Could you explain [what you want to understand]? This will help me provide more relevant feedback."

### When Praising Good Work
"I really appreciated [specific thing] in [location] because [why it's good]. This demonstrates [good practice/principle] and will help [benefit] going forward."

### When Sharing Resources
"For [topic], you might find [resource] helpful. It shows [relevant information] that applies to this situation because [connection]. Specifically, [section/example] demonstrates [relevant concept]."

### When Suggesting Alternatives
"What do you think about trying [alternative approach] instead of [current approach] in [location]? It might [benefit] because [reasoning]. We used a similar pattern in [reference] when we faced [similar situation]."

### When Addressing Consistency
"I noticed we handle [similar situation] differently in [location A] vs [location B]. In [location A] we do [approach A], while here we do [approach B]. For consistency, would it make sense to standardize on [preferred approach]? What are your thoughts on this?"

### When Providing Context
"Just to make sure I have the full picture - is this change intended to [purpose/goal]? Understanding that will help me evaluate whether [specific aspect] aligns with our objectives. If there are constraints I should be aware of around [factor], please let me know."

## 10. Psychological Aspects of Review Comments

### The Feedback Reception Curve
Authors typically process feedback in stages:
1. **Initial Reaction**: Immediate emotional response (defensiveness, confusion, curiosity)
2. **Cognitive Processing**: Trying to understand what the feedback means
3. **Decision Making**: Determining what changes to make, if any
4. **Implementation**: Actually making the changes
5. **Reflection**: Learning from the experience for future work

Effective comments consider this curve and aim to:
- Minimize defensive reactions through respectful delivery
- Facilitate cognitive processing through specificity and clarity
- Enable good decision making through actionable suggestions
- Support implementation through clear instructions
- Promote learning through explanatory content

### Common Cognitive Biases to Awareness
- **Confirmation Bias**: Tendency to interpret feedback as confirming pre-existing beliefs
- **Negativity Bias**: Giving more weight to negative feedback than positive
- **Dunning-Kruger Effect**: Less competent authors overestimating their ability to judge feedback quality
- **Anchoring Bias**: First feedback received disproportionately influencing subsequent interpretation
- **Frame-of-reference Bias**: Interpreting feedback through personal experience lens rather than objective criteria
- **Status Quo Bias**: Preferring to keep things as they are rather than make suggested changes
- **Authority Bias**: Giving undue weight to feedback based on reviewer's perceived seniority rather than content
- **Bandwagon Effect**: Being influenced by perceived popularity of certain opinions

### Emotional Intelligence in Feedback
- **Self-awareness**: Recognizing your own biases, mood, and tendencies when giving feedback
- **Self-regulation**: Managing frustration, impatience, or the urge to be overly critical
- **Empathy**: Understanding how the author might receive your feedback
- **Social Skills**: Delivering feedback in ways that maintain positive relationships
- **Motivation**: Framing feedback to encourage rather than discourage effort

### Creating Psychological Safety
- **Belonging Cues**: Signals that the author is valued and respected
- **Vulnerability Loops**: Appropriate sharing of uncertainty or mistakes by reviewers
- **Clear Expectations**: Transparent standards for what constitutes good feedback
- **Error Tolerance**: Environment where mistakes are seen as learning opportunities
- **Purpose Connection**: Linking feedback to meaningful goals and values
- **Agency Preservation**: Respecting author's autonomy in deciding how to respond
- **Fairness Perception**: Belief that feedback is applied consistently and objectively

## 11. Practical Exercise

**Exercise**: Improving Review Comments

You're reviewing a pull request that adds a new feature for exporting user data in multiple formats. Examine the following review comments and improve them according to the principles discussed:

### Part 1: Identifying Problems with Existing Comments
Review these comments and identify what makes them less effective:
1. "This code is messy and hard to read."
2. "You should use a switch statement here instead of all these if-else blocks."
3. "Why did you even do it this way? It's obviously wrong."
4. "Consider using polymorphism to handle the different export formats instead of this repetitive code."
5. "Nice job on the error handling - it's comprehensive."

### Part 2: Rewriting Comments for Effectiveness
Take each of the comments above and rewrite them to be:
- More specific and actionable
- Respectful and educational in tone
- Context-aware
- Focused on important issues
- Valuable for learning

### Part 3: Writing New Comments
Imagine you're reviewing the export feature and notice:
- The CSV export function doesn't properly escape commas within fields
- The JSON export uses string concatenation instead of a proper JSON library
- All export functions duplicate the same permission checking logic
- The XML export creates vulnerable to XXE attacks if user input isn't sanitized
- The PDF export correctly handles page breaks and formatting

Write 3-5 effective review comments that address these issues following the best practices discussed.

## 12. Definition of Done

Effective review comments in code review are complete when:
- [ ] You've provided specific, actionable feedback rather than vague impressions
- [ ] You've explained the reasoning behind your suggestions rather than just stating opinions
- [ ] You've maintained a respectful, constructive tone that preserves psychological safety
- [ ] You've considered the author's likely experience level and background
- [ ] You've focused on significant issues rather than trivialities or personal preferences
- [ ] You've acknowledged what was done well alongside areas for improvement
- [ ] You've provided concrete examples or alternatives when suggesting changes
- [ ] You've connected feedback to team standards, principles, or best practices when relevant
- [ ] You've asked clarifying questions when uncertain about intent or constraints
- [ ] You've avoided assuming negative intent or lack of competence on the author's part
- [ ] You've made it clear that feedback is about improving code, not judging the author
- [ ] You've considered the change's context including constraints, history, and purpose
- [ ] You've framed feedback to help the author learn and grow rather than just fix issues
- [ ] You've balanced negative feedback with positive recognition appropriately
- [ ] You've made your comments easy to locate and reference in the code
- [ ] You've considered whether your feedback might be better discussed synchronously
- [ ] You've reviewed your own comments for tone, clarity, and effectiveness before submitting
- [ ] You've remained open to learning that your suggestions might not be feasible or optimal
- [ ] You've considered the cumulative impact of all your feedback on this review