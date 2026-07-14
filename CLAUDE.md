# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Purpose

This is a **keleo-labs** repository containing JSON-formatted software engineering practices and methods for abstracted infrastructure platforms. It uses the SEMAT Essence-inspired schema defined by [Keleo Studio](https://github.com/keleo-labs/keleo-studio) (a Next.js application for authoring, composing, and visualizing practices).

This is a content repository, not an application. There is no build system, test suite, or runtime code. The primary artifacts are JSON files organized into three directories:

- `baseline/` -- PracticeBaseline files defining core ontologies (Alphas, ActivitySpaces, Competencies, NarrativeTypes)
- `practices/` -- Practice extensions that build on a baseline via `baselinePracticeName`
- `methods/` -- Composed methods combining a baseline with multiple practices via `practiceNames`

PNG files alongside JSONs are "Overview of Concerns" diagrams exported from Keleo Studio showing the Alpha hierarchy across Value/Solution/Endeavor focus areas.

## Validation

Validation requires Keleo Studio (typically at `../adoptionframework`):

```bash
cd ../adoptionframework
node validate-schema.js path/to/practice.json      # schema only
node validate-full.js path/to/practice.json         # schema + logical integrity
```

## Content Model

The three baselines share the same Value/Solution/Endeavor focus structure but specialize the Alphas:

| Baseline | Domain | Key Differentiators |
|----------|--------|-------------------|
| Platform Adoption Essentials | General platform transformations | Root baseline; generic Alpha names (Platform, Requirements, Team) |
| IDP Essentials | Internal Developer Platforms | Aliases Alphas to IDP terms (Developer Portal, Workload, Developer Experience Needs); adds DevEx competencies and activity spaces |
| Infrastructure Automation Essentials | Infrastructure as Code | Adds Managed Asset and Asset Governance Alphas; extends with IaC lifecycle activity spaces |

Practices reference a baseline by exact string name in `baselinePracticeName`. Methods reference practices by exact string name in `practiceNames`. All cross-references are string-based; never embed full objects where a string reference is expected.

## Key Schema Constraints When Editing JSON

- New Alphas must declare `contributesTo` linking to a baseline or dependency Alpha
- Activities must reference a valid `activitySpaceName` from the baseline
- Personas must have non-empty `competencies` arrays matching baseline Competency names
- Activities reference PersonaGroups (not Personas directly) via `involves`
- WorkProducts require minimum 3 `levelsOfDetail`
- When redeclaring baseline Alphas, preserve state names and count (can enrich with checklists)
- Narratives require both `name` and `narrativeName` properties
- `practiceElementAliases` are display-only; all structural references must use the canonical baseline name

## Relationship Between Files

```
Platform Adoption Essentials (baseline)
  |
  +-- Team Structure & Cognitive Load (practice)
  +-- Organizational Evolution & Sensing (practice)
  +-- Team Topologies Lifecycle (practice, depends on above two)
  |
  +-- Team Topologies (method: baseline + 3 practices above)

IDP Essentials (baseline, extends Platform Adoption Essentials)
  |
  +-- Platform Engineering (CNCF) (practice, PNG only in this repo)
  +-- (reuses Team Topologies practices)
  |
  +-- Platform Engineering (method: IDP baseline + CNCF practice + Team Topologies practices)
```

## Generating New Practices

Keleo Studio includes LLM prompts in `../adoptionframework/prompts and instructions/`:

- **full-process-gem.md**: 11-phase analytical pipeline (Personas through Final Output)
- **phase 1 gem.md** + **phase 2 gem.md**: Research-first approach (human-readable report, then JSON conversion)

Critical: treat the baseline as a custom proprietary ontology. Suppress pre-trained SEMAT Essence knowledge. Only use elements explicitly present in the uploaded baseline JSON. Validate all string references against the baseline.

## Integration with Keleo Studio

```bash
cd ../adoptionframework
npm install
npm run dev
# Access at http://localhost:3000
```

Key features: Practice Author (WYSIWYG editor), Method Builder (drag-and-drop composition), Flow Visualizer (Kanban pattern boards), Library (import/export/browse).
