---
parent: Decisions
nav_order: 21
---
# Add Next Steps Section to AI Template

status: accepted
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

---

## Feedback Log

### Implementation Review (2025-10-27)

**Implementation Date:** 2025-10-27
**Reviewer:** ADR Review Skill (Claude Code)
**Review Type:** Post-implementation validation

#### Implementation Status: ✅ Fully Implemented

All confirmation criteria have been successfully met:

#### Confirmation Criteria Status

✅ **Next Steps section added to template/adr-template-ai.md**
Evidence: Lines 115-136 in template/adr-template-ai.md contain the complete Next Steps section

✅ **Section positioned after Test Expectations**
Evidence: Test Expectations section ends at line 113, Next Steps begins at line 116

✅ **Section positioned before Dependencies**
Evidence: Next Steps ends at line 136, Dependencies begins at line 139

✅ **Includes Immediate Actions subsection**
Evidence: Lines 120-124 contain the Immediate Actions subsection with bulleted list format

✅ **Includes Implementation Sequence subsection**
Evidence: Lines 126-130 contain the Implementation Sequence subsection with numbered list format (sequential steps)

✅ **Includes Ownership subsection**
Evidence: Lines 132-136 contain the Ownership subsection with primary implementer, supporting roles, and stakeholders fields

✅ **Template files synchronized**
Evidence: Both template/adr-template-ai.md and docs/decisions/adr-template-ai.md contain identical Next Steps sections

✅ **CLAUDE.md documentation updated**
Evidence: Line 163 in CLAUDE.md includes Next Steps in the extended template table, correctly positioned between Test Expectations and Dependencies

#### Additional Achievements

✅ **Bonus: Timeline section removed (ADR-0020)**
The implementation also removed the Timeline section as documented in ADR-0020, reducing template complexity and eliminating duplicate tracking

✅ **Clean implementation with proper structure**
All subsections follow MADR conventions with appropriate placeholders and HTML comments for guidance

✅ **Git commit follows project conventions**
Commit c12d9e0 includes proper attribution, clear message, and comprehensive change description

#### Files Modified

* `template/adr-template-ai.md` - Primary template file (+23 lines Next Steps, -9 lines Timeline)
* `docs/decisions/adr-template-ai.md` - Documentation mirror (+23 lines Next Steps, -9 lines Timeline)
* `docs/decisions/0021-add-next-steps-section-to-ai-template.md` - This ADR (+130 lines)
* `CLAUDE.md` - Framework documentation (+2 lines: Next Steps description, ADR-0021 reference; -1 line: Timeline removed)

#### Actual Outcomes

* **Actionable guidance provided:** AI agents now have explicit, structured guidance for beginning implementation
* **Improved template flow:** The sequence (Test Expectations → Next Steps → Dependencies) creates a logical progression
* **Validation mechanism:** Documenting next steps forces teams to think through implementability
* **Template remains optional:** Proper use of HTML comments preserves flexibility
* **Synchronization maintained:** Both template locations updated consistently

#### Challenges Encountered

None. Implementation was straightforward and completed in a single commit with all requirements met.

#### Lessons Learned

* **Bundling related changes works well:** Implementing ADR-0020 (remove Timeline) and ADR-0021 (add Next Steps) together was efficient and created a clean changeset
* **Template structure is intuitive:** The positioning between Test Expectations and Dependencies creates a natural flow that aligns with how teams think about implementation
* **Subsections provide clarity:** Breaking Next Steps into three distinct subsections (Immediate Actions, Implementation Sequence, Ownership) provides clear structure without being prescriptive

#### Recommendations

* **Monitor usage patterns:** Track how teams use the Next Steps section to identify if additional guidance or examples would be helpful
* **Consider examples:** Future documentation could include concrete examples of well-written Next Steps sections
* **Evaluate necessity:** After real-world usage, assess whether all three subsections are consistently used or if some could be consolidated
* **Update status to accepted:** ADR-0021 is currently marked as "proposed" but should be updated to "accepted" now that implementation is complete
