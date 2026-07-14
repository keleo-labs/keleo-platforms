# keleo-platforms

Baseline practices, practice extensions, and composed methods for **abstracted infrastructure platforms** -- authored and visualized with [Keleo Studio](https://github.com/keleo-labs/keleo-studio).

Part of the [keleo-labs](https://github.com/keleo-labs) organization.

## What's In This Repository

This repository provides a curated set of JSON-formatted practices following the SEMAT Essence-inspired schema. Each practice models a domain through **Alphas** (essential elements of concern), **Activities**, **WorkProducts**, **Personas**, **Patterns**, and **Narratives** -- organized across three areas of concern: **Value**, **Solution**, and **Endeavor**.

### Baselines

Foundational ontologies defining the core Alphas, activity spaces, competencies, and narrative frameworks. All practices and methods in this repository build on one of these baselines.

| Baseline | Domain |
|----------|--------|
| [Platform Adoption Essentials](baseline/platform-adoption-essentials.json) | General platform transformations |
| [IDP Essentials](baseline/idp-essentials.json) | Internal Developer Platforms |
| [Infrastructure Automation Essentials](baseline/infrastructure-automation-essentials.json) | Infrastructure as Code |

See [baseline/README.md](baseline/README.md) for details and concern diagrams.

### Practices

Extensions that add domain-specific Alphas, activities, personas, and patterns to a baseline.

| Practice | Baseline | Focus |
|----------|----------|-------|
| [Team Structure & Cognitive Load](practices/team-structure--cognitive-load.json) | Platform Adoption Essentials | Team types, interaction modes, cognitive load management |
| [Organizational Evolution & Sensing](practices/organizational-evolution--sensing.json) | Platform Adoption Essentials | Continuous topology adaptation and platform-as-product |
| [Team Topologies Lifecycle](practices/team-topologies-lifecycle.json) | Platform Adoption Essentials | Orchestration of team structure and org evolution practices |

See [practices/README.md](practices/README.md) for details.

### Methods

Composed methodologies combining a baseline with multiple practices.

| Method | Baseline | Practices |
|--------|----------|-----------|
| [Team Topologies](methods/team-topologies.json) | Platform Adoption Essentials | Team Structure & Cognitive Load, Organizational Evolution & Sensing, Team Topologies Lifecycle |
| [Platform Engineering](methods/platform-engineering.json) | IDP Essentials | Platform Engineering (CNCF), Team Topologies Lifecycle, Organizational Evolution & Sensing, Team Structure & Cognitive Load |

See [methods/README.md](methods/README.md) for details and concern diagrams.

## Viewing and Editing

These JSON files are best viewed and edited using **[Keleo Studio](https://github.com/keleo-labs/keleo-studio)**, which provides:

- **Practice Author** -- WYSIWYG editor for practice JSON
- **Method Builder** -- Drag-and-drop composition of practices into methods
- **Flow Visualizer** -- Kanban pattern boards and Sankey flow diagrams
- **Library** -- Browse, import, and export practice collections

```bash
# Run Keleo Studio locally
cd ../adoptionframework    # or wherever keleo-studio is cloned
npm install
npm run dev
# Open http://localhost:3000
```

## Generating New Practices

Keleo Studio includes LLM prompts for generating validated practices from source documentation:

- **Full 11-phase process** (`full-process-gem.md`): Personas, Alphas, WorkProducts, Activities, PersonaGroups, Narratives, Lifecycle Patterns, Narrative Patterns, Practice Formation, Logical Integrity, Final Output
- **Two-phase research process** (`phase 1 gem.md` + `phase 2 gem.md`): Generate a human-readable research report first, then convert to validated JSON

Prompts are in the Keleo Studio `prompts and instructions/` directory.

## Validation

```bash
cd ../adoptionframework
node validate-schema.js path/to/practice.json      # schema validation
node validate-full.js path/to/practice.json         # schema + logical integrity
```

## License

Apache License 2.0 -- see [LICENSE](LICENSE).
