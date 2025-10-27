---
parent: Decisions
nav_order: 21
---
# Add Next Steps Section to AI Template

status: proposed
date: 2025-10-27
decision-makers: Owen Zanzal

## Context and Problem Statement

The AI-extended ADR template helps guide AI agents through implementation of architectural decisions. However, once a decision is made, the ADR doesn't provide clear guidance on what concrete actions should happen next. AI agents and team members would benefit from having explicit, actionable next steps documented alongside the decision. How can we better bridge the gap between decision and implementation?

## Decision Drivers

* AI agents need explicit, actionable guidance to begin implementation
* The gap between "decision made" and "implementation started" often causes delays
* Teams benefit from having a clear action plan documented with the decision
* Next steps help validate that the decision is actually implementable
* Documenting next steps makes the ADR more actionable and less theoretical
* The AI-extended template already focuses on implementation guidance

## Considered Options

* Add a dedicated "Next Steps" section to the AI template
* Use the existing "More Information" section for next steps
* Add next steps to the "Test Expectations" section
* Do nothing - let teams determine next steps on their own

## Decision Outcome

Chosen option: "Add a dedicated 'Next Steps' section to the AI template", because it provides clear, actionable guidance that bridges the decision-to-implementation gap, makes ADRs more practical for AI agents, and helps validate that decisions are implementable.

### Consequences

* Good, because AI agents have explicit guidance on how to begin implementation
* Good, because it forces decision-makers to think through practical implementation steps
* Good, because next steps validate that the decision is actually implementable
* Good, because it reduces the gap between decision and action
* Good, because it makes ADRs more actionable and less theoretical
* Neutral, because it adds another optional section to an already extensive template
* Neutral, because some next steps may become outdated as implementation progresses
* Bad, because teams may struggle to define concrete next steps for complex decisions

### Confirmation

Add the "Next Steps" section to template/adr-template-ai.md after the "Test Expectations" section. The section should include fields for immediate actions, sequential steps, and ownership/assignment.

## Pros and Cons of the Options

### Add a dedicated "Next Steps" section to the AI template

* Good, because it provides a standardized location for actionable implementation guidance
* Good, because AI agents can directly execute or prioritize these steps
* Good, because documenting next steps forces validation that the decision is implementable
* Good, because it bridges the gap between architectural decision and practical implementation
* Good, because it aligns with the AI template's focus on implementation guidance
* Neutral, because it adds another section to an already comprehensive template
* Bad, because next steps may become outdated as implementation evolves
* Bad, because not all decisions have clear, discrete next steps

### Use the existing "More Information" section for next steps

* Good, because it doesn't add another dedicated section
* Good, because "More Information" is already flexible and accommodates various content
* Neutral, because teams already can document next steps there if they choose
* Bad, because next steps would not be standardized or easily discoverable
* Bad, because it doesn't give next steps the prominence they deserve for AI-driven workflows
* Bad, because AI agents would need to parse unstructured text to find actionable steps

### Add next steps to the "Test Expectations" section

* Good, because tests and next steps are closely related to implementation
* Good, because it keeps the template concise by combining related concepts
* Neutral, because tests are a specific type of next step (validation)
* Bad, because it conflates two different concerns (what to test vs what to implement)
* Bad, because next steps include more than just testing activities
* Bad, because it makes the "Test Expectations" section less focused

### Do nothing - let teams determine next steps on their own

* Good, because it keeps the template simpler and less prescriptive
* Good, because teams have flexibility to manage implementation however they prefer
* Neutral, because teams can already document next steps in "More Information" if desired
* Bad, because it misses an opportunity to provide actionable guidance for AI agents
* Bad, because the gap between decision and implementation remains unaddressed
* Bad, because it doesn't align with the AI template's goal of guiding implementation

## More Information

The "Next Steps" section should be positioned after "Test Expectations" and before "Dependencies" in the AI-specific sections. This placement creates a natural flow:

1. **Test Expectations** - Define how to validate success
2. **Next Steps** - Define what to do to achieve that success
3. **Dependencies** - Define what's needed to complete those steps

Suggested structure for the Next Steps section:

```markdown
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
```

This structure provides:

* **Immediate Actions** - Quick wins or prerequisite tasks
* **Implementation Sequence** - Ordered steps for complex implementations
* **Ownership** - Clear accountability and coordination

The section is optional and can be removed if next steps are tracked in external project management tools. However, for AI-driven workflows, having explicit next steps co-located with the decision significantly improves the agent's ability to execute effectively.
