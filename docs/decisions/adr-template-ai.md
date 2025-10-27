---
parent: Decisions
nav_order: 101
title: ADR Template for AI-Driven Development
---
# {short title, representative of solved problem and found solution}

## Context and Problem Statement

{Describe the context and problem statement, e.g., in free form using two to three sentences or in the form of an illustrative story. You may want to articulate the problem in form of a question and add links to collaboration boards or issue management systems.}

<!-- This is an optional element. Feel free to remove. -->
## Decision Drivers

* {decision driver 1, e.g., a force, facing concern, …}
* {decision driver 2, e.g., a force, facing concern, …}
* … <!-- numbers of drivers can vary -->

## Considered Options

* {title of option 1}
* {title of option 2}
* {title of option 3}
* … <!-- numbers of options can vary -->

## Decision Outcome

Chosen option: "{title of option 1}", because {justification. e.g., only option, which meets k.o. criterion decision driver | which resolves force {force} | … | comes out best (see below)}.

<!-- This is an optional element. Feel free to remove. -->
### Consequences

* Good, because {positive consequence, e.g., improvement of one or more desired qualities, …}
* Bad, because {negative consequence, e.g., compromising one or more desired qualities, …}
* … <!-- numbers of consequences can vary -->

<!-- This is an optional element. Feel free to remove. -->
### Confirmation

{Describe how the implementation / compliance of the ADR can/will be confirmed. Is there any automated or manual fitness function? If so, list it and explain how it is applied. Is the chosen design and its implementation in line with the decision? E.g., a design/code review or a test with a library such as ArchUnit can help validate this. Note that although we classify this element as optional, it is included in many ADRs.}

<!-- This is an optional element. Feel free to remove. -->
## Pros and Cons of the Options

### {title of option 1}

<!-- This is an optional element. Feel free to remove. -->
{example | description | pointer to more information | …}

* Good, because {argument a}
* Good, because {argument b}
<!-- use "neutral" if the given argument weights neither for good nor bad -->
* Neutral, because {argument c}
* Bad, because {argument d}
* … <!-- numbers of pros and cons can vary -->

### {title of other option}

{example | description | pointer to more information | …}

* Good, because {argument a}
* Good, because {argument b}
* Neutral, because {argument c}
* Bad, because {argument d}
* …

<!-- This is an optional element. Feel free to remove. -->
## More Information

{You might want to provide additional evidence/confidence for the decision outcome here and/or document the team agreement on the decision and/or define when/how this decision the decision should be realized and if/when it should be re-visited. Links to other decisions and resources might appear here as well.}

---

# AI-Specific Sections

The sections below extend the standard MADR template for AI-driven development workflows.
These are optional and can be removed if not using AI agents for implementation.
See [ADR-0019](0019-add-claude-md-for-agent-coding-support.md) for the full framework.

<!-- This is an optional element. Feel free to remove. -->
## AI Guidance Level

{Defines how much freedom the AI agent has when implementing this decision:}

* **strict** - Follow exact specifications with minimal interpretation
* **flexible** - Interpret intent with some creativity within constraints
* **exploratory** - Research alternatives and propose additional options

{Chosen level: [strict | flexible | exploratory]}

<!-- This is an optional element. Feel free to remove. -->
## AI Tool Preferences

{Specify which AI tools/models should be used for implementation and their parameters.}

* Primary tool: {e.g., "Claude Code for implementation"}
* Secondary tool: {e.g., "GitHub Copilot for code completion"}
* Model preferences: {e.g., "Use Claude Sonnet 4.5 for complex reasoning"}
* Parameters: {Any specific settings or constraints}

<!-- This is an optional element. Feel free to remove. -->
## Test Expectations

{Specific tests that validate alignment with this ADR's intent. This follows Test-Driven Development (TDD) principles where tests are written before implementation.}

* Test 1: {Description of what should be validated}
* Test 2: {Description of what should be validated}
* Acceptance criteria: {When is the implementation considered complete?}
* … <!-- numbers of tests can vary -->

<!-- This is an optional element. Feel free to remove. -->
## Next Steps

{Concrete, actionable steps to begin implementing this decision. These help bridge the gap between decision and implementation.}

### Immediate Actions

* {Action 1: What should happen first}
* {Action 2: What should happen next}
* … <!-- ordered list of immediate actions -->

### Implementation Sequence

1. {Step 1: First major implementation milestone}
2. {Step 2: Second major implementation milestone}
3. … <!-- ordered sequence of implementation steps -->

### Ownership

* Primary implementer: {Who will lead implementation}
* Supporting roles: {Who else needs to be involved}
* Stakeholders to notify: {Who should be informed when implementation begins}

<!-- This is an optional element. Feel free to remove. -->
## Dependencies

{Related ADRs, system components, or external factors that must be considered during implementation.}

* ADR-NNNN: {Related decision that impacts this one}
* Component/Module: {System components affected by this decision}
* External dependencies: {Libraries, APIs, or services required}
* … <!-- numbers of dependencies can vary -->

<!-- This is an optional element. Feel free to remove. -->
## Risk Assessment

{Technical and business risks associated with this decision.}

### Technical Risks

* {Risk 1 and mitigation strategy}
* {Risk 2 and mitigation strategy}
* … <!-- numbers of risks can vary -->

### Business Risks

* {Risk 1 and mitigation strategy}
* {Risk 2 and mitigation strategy}
* … <!-- numbers of risks can vary -->

<!-- This is an optional element. Feel free to remove. -->
## Human Review

{Whether human approval is required before or after AI implementation.}

* Review required: {yes | no}
* Reviewers: {List of people who must approve}
* Review stage: {before implementation | after implementation | both}
* Review criteria: {What specifically should be reviewed}

<!-- This is an optional element. Feel free to remove. -->
## Feedback Log

{Notes from AI agents or team members about implementation results. This section is updated after implementation to record actual outcomes and learnings.}

### Implementation Notes

* {Date}: {What happened during implementation}
* {Date}: {Challenges encountered and how they were resolved}
* … <!-- entries added over time -->

### AI Agent Feedback

* {Tool name} on {date}: {Observations about the ADR's clarity, completeness, or effectiveness}
* … <!-- entries added over time -->

<!-- This is an optional element. Feel free to remove. -->
## Learning Reinforcement

{Key insights that should be carried forward to future decisions. This section captures organizational learning for improving future ADRs.}

* {Insight 1: What worked well}
* {Insight 2: What could be improved}
* {Insight 3: Patterns to replicate or avoid}
* … <!-- insights accumulated over time -->
