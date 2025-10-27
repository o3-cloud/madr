---
parent: Decisions
nav_order: 20
---
# Remove Timeline Section from AI Template

status: accepted
date: 2025-10-27
decision-makers: Owen Zanzal

## Context and Problem Statement

The AI-extended ADR template includes a "Timeline" section that specifies implementation deadlines and review dates. In practice, implementation timelines are better tracked in project management tools, issue trackers, or the ADR's metadata fields (like the date field). How should we handle timeline information in the AI template to avoid duplication and maintain simplicity?

## Decision Drivers

* Timeline information often becomes stale and requires frequent updates
* Project management tools (Jira, Linear, GitHub Issues) are better suited for tracking deadlines
* The ADR's date field already captures when decisions are made/updated
* Separating timeline tracking from architectural reasoning keeps ADRs focused
* Reducing optional sections makes the template less overwhelming

## Considered Options

* Remove the Timeline section entirely
* Keep Timeline but simplify it to only "Review date"
* Move Timeline to More Information section as a note
* Keep Timeline section as-is

## Decision Outcome

Chosen option: "Remove the Timeline section entirely", because timelines belong in project management systems rather than architectural decision records, and removing this section reduces maintenance burden while keeping ADRs focused on architectural rationale.

### Consequences

* Good, because ADRs remain focused on architectural decisions rather than project management
* Good, because it reduces the number of optional sections, making the template less intimidating
* Good, because it eliminates duplicate tracking between ADRs and project management tools
* Good, because it reduces maintenance burden (no need to update stale deadlines in ADRs)
* Neutral, because teams that find timeline information valuable can still add it in "More Information"
* Bad, because teams lose a standardized place to document when decisions should be revisited

### Confirmation

Remove the Timeline section from template/adr-template-ai.md and update the corresponding documentation. The AI template should no longer include implementation deadline or review date fields.

## Pros and Cons of the Options

### Remove the Timeline section entirely

* Good, because it eliminates duplicate information between ADRs and project management tools
* Good, because it reduces the number of optional sections in an already extensive template
* Good, because timelines often become stale and maintaining them in ADRs creates noise
* Good, because architectural decisions should be timeless - focused on "why" not "when"
* Bad, because some teams may find value in having timeline information co-located with decisions
* Neutral, because teams can still document timeline information in "More Information" if needed

### Keep Timeline but simplify it to only "Review date"

* Good, because review dates help ensure decisions are periodically reassessed
* Good, because it's a compromise that keeps some temporal information
* Bad, because even review dates require maintenance and often become stale
* Bad, because it still creates overlap with project management tools
* Bad, because it doesn't solve the fundamental issue of timeline tracking belonging elsewhere

### Move Timeline to More Information section as a note

* Good, because it provides an example of what could go in "More Information"
* Good, because it's more flexible than a dedicated section
* Neutral, because it doesn't eliminate the section but makes it less prominent
* Bad, because it still encourages tracking timeline information in ADRs

### Keep Timeline section as-is

* Good, because it maintains the current structure for teams already using it
* Good, because implementation deadlines can provide context for understanding urgency
* Bad, because timelines belong in project management systems, not architectural documentation
* Bad, because it adds maintenance burden to keep dates current
* Bad, because the template is already extensive with many optional sections

## More Information

The Timeline section was originally introduced in ADR-0019 as part of the AI-extended template. It included:

* Implementation deadline
* Review date
* Triggers for revision

These elements serve project management purposes rather than architectural documentation purposes. Teams that need this information should track it in their project management tools and can reference those tools in the ADR's "More Information" section if needed.

The date field in the ADR metadata already captures when decisions are made and updated, providing sufficient temporal context for architectural purposes.
