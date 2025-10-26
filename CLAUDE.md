# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

MADR (Markdown Architectural Decision Records) is a lightweight template and tooling project for documenting architectural decisions using Markdown. The project itself is primarily a documentation repository that provides ADR templates and maintains a Jekyll-based website at <https://adr.github.io/madr/>.

## Repository Structure

The repository has two main content areas:

- `template/`: Contains the canonical ADR templates that are distributed via npm. These files are the core product:
  - `adr-template.md` - Full template with all sections and explanations
  - `adr-template-minimal.md` - Minimal template with only mandatory sections
  - `adr-template-bare.md` - All sections, no explanations
  - `adr-template-bare-minimal.md` - Minimal sections, no explanations
  - `0000-use-markdown-architectural-decision-records.md` - Example ADR for adopting MADR itself
  - `i18n/` - Internationalized versions of templates (e.g., German)

- `docs/`: Jekyll-based documentation site that mirrors and explains the templates. Key files:
  - `index.md` - Main documentation page
  - `examples.md` - Examples of MADRs
  - `decisions/` - ADRs documenting MADR's own design decisions (meta-ADRs)
  - `_config.yml` - Jekyll configuration using "Just the Docs" theme

## Branch Strategy

This project follows git flow with specific conventions:

- `develop` - Main development branch (NOT `main`). All PRs should target this branch.
- `gh-pages` - Production website at <https://adr.github.io/madr/> (released versions only)
- `release/vX` - Branch for each major version (e.g., `release/v4`) to allow patches to releases

**Important**: When working on templates or documentation, target the `develop` branch. The develop version is previewed at <https://develop--madr-develop.netlify.app/>.

## Development Commands

### Running the Documentation Site Locally

Jekyll is used to render the `docs/` directory.

```bash
# Install dependencies
bundle install

# Start local server with live reload
jekyll serve --livereload
```

Then visit <http://localhost:4000/madr/>

On Windows, use Docker:
```bash
docker run -p 4000:4000 --rm -v "$(pwd)/docs":/site bretfisher/jekyll-serve
```

### Linting

The project uses markdownlint for consistent Markdown formatting:

```bash
# Lint markdown files (typically done via GitHub Actions)
markdownlint '**/*.md'
```

Configuration is in `.markdownlint.yml` with these key rules:
- MD013 (line length) is disabled - follows one-sentence-per-line rule
- MD024 (duplicate headings) is disabled - ADRs often repeat headings like "Examples"

### Package Management

The templates are distributed via npm:

```bash
# Install locally (users would run this)
npm install madr

# Publishing (maintainers only)
# Uses release-it - configured in .release-it.json
npm run release
```

## Template Synchronization

The templates in `template/` and their counterparts in `docs/decisions/` must be kept in sync:

- `template/adr-template.md` → `docs/decisions/adr-template.md` (with YAML front matter added)
- `template/0000-use-markdown-architectural-decision-records.md` → `docs/decisions/0000-use-markdown-architectural-decision-records.md`

When editing templates, update both locations. The `docs/` version requires Jekyll front matter:
```yaml
---
parent: Decisions
nav_order: 100
title: ADR Template
---
```

## ADR Naming Convention

ADR filenames follow the pattern: `NNNN-title-with-dashes.md`

- `NNNN` - Four-digit consecutive number (assumes max 9,999 ADRs)
- Title uses lowercase with dashes
- `.md` extension

Example: `0001-use-markdown-for-adrs.md`

## Key Design Decisions

The project's own ADRs (in `docs/decisions/`) document important design choices:

- **0000**: Use Markdown for ADRs (the foundational decision)
- **0002**: Do not use numbers in headings
- **0005**: Use dashes in filenames
- **0006**: Use names (not numbers) as identifiers in links
- **0008**: Add status field to ADRs
- **0010**: Support categories via subdirectories
- **0013**: Use YAML front matter for metadata
- **0014**: Allow neutral arguments in pros/cons
- **0019**: Add CLAUDE.md for better agent coding support

## Release Process

When releasing a new version (maintainers only):

1. Update examples in `docs/index.md` and `docs/examples.md`
2. Update the concrete decisions in `docs/decisions/*` with new template
3. Adapt version reference in `template/0000-use-markdown-architectural-decision-records.md`
4. Sync template files from `template/` to `docs/decisions/`
5. Copy `.markdownlint.yml` to `template/.markdownlint.yml`
6. Update `CHANGELOG.md`
7. Update `package.json` version and publish using `release-it`
8. Create GitHub release using `github-release-from-changelog`
9. Merge `develop` into `gh-pages`

## ADR-Driven AI Development Framework

MADR supports an extended framework for combining ADRs with AI-assisted development and Test-Driven Development (TDD). This framework positions ADRs as the central artifact that guides both human and AI collaboration.

### Core Principles

**ADRs as Anchors** — Each decision is documented with context, options, rationale, and outcomes. ADRs serve as the single source of truth for architectural intent.

**AI as Executor** — AI agents use ADRs (and optional specifications) to generate implementation code that aligns with documented decisions.

**TDD as Guardrail** — Tests are written first to validate that AI output satisfies the ADR's intent and requirements.

**Feedback Loop** — Implementation results feed back into new or updated ADRs, improving future outcomes and creating organizational learning.

### Extended ADR Template for AI Agents

When using ADRs to guide AI development, consider extending the standard MADR template with these additional sections:

| Section | Description |
|---------|-------------|
| **AI Guidance Level** | Defines how much freedom the AI has: strict (follow exact specifications), flexible (interpret intent with some creativity), or exploratory (research and propose alternatives) |
| **AI Tool Preferences** | Which AI tools/models to use and their parameters (e.g., "Use Claude Code for implementation, GitHub Copilot for completion") |
| **Test Expectations** | Specific tests that validate alignment with the ADR's intent (TDD approach) |
| **Dependencies** | Related ADRs or system components that must be considered |
| **Timeline** | When this ADR should be revisited or reviewed |
| **Risk Assessment** | Technical and business risks associated with this decision |
| **Human Review** | Whether human approval is required before implementation |
| **Feedback Log** | Notes from AI agents or team members about implementation results |
| **Learning Reinforcement** | Key insights that should be carried forward to future decisions |

These extensions transform ADRs from static documentation into dynamic guidance systems that improve over time.

### Development Workflow

The AI-driven development workflow creates a continuous improvement cycle:

1. **Write ADR** — Document the architectural decision with context, alternatives, and expected consequences
2. **Generate Tests (TDD)** — Create tests that validate the ADR's requirements before implementation
3. **AI Generates Code** — AI agent uses the ADR and tests to generate implementation
4. **Run Tests** — Validate that implementation aligns with ADR intent
5. **Deploy & Record Outcome** — On success, deploy and document actual results in the ADR
6. **Revise ADR or Tests** — On failure, update either the ADR (if requirements were unclear) or tests (if they don't properly validate intent)
7. **Feedback to ADR System** — All outcomes feed back to improve future ADRs and AI guidance

### Feedback and Evolution

To maximize learning from this framework:

- **Version ADRs** — Tie decisions to specific releases or branches for traceability
- **Measure Drift** — Compare AI output against ADR intent over time to identify where guidance needs improvement
- **Automate Insights** — Enable AI to analyze ADR patterns and suggest improvements
- **Continuous Improvement** — Each ADR update refines both human reasoning and AI understanding

This creates a system where development becomes more transparent, traceable, and adaptive over time. The ADR becomes a living artifact that unifies human architectural reasoning with AI execution capabilities.

### Benefits

- **Transparency** — All architectural decisions and their rationale are explicitly documented
- **Traceability** — Implementation can be traced back to specific decisions and requirements
- **Adaptability** — The feedback loop enables continuous improvement of both decisions and implementations
- **Knowledge Transfer** — ADRs become a shared language between humans and AI agents
- **Quality Assurance** — TDD ensures AI output meets documented requirements

See `docs/decisions/0019-add-claude-md-for-agent-coding-support.md` for the full ADR documenting this framework.

## License

Dual-licensed under MIT OR CC0-1.0. Users can choose either license.
