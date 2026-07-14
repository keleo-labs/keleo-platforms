# Baselines

PracticeBaseline files define the foundational ontology that all practices and methods build upon. A baseline establishes the **Focuses** (areas of concern), **Alphas** (essential elements with progressive states), **ActivitySpaces** (categories of work), **Competencies** (skills with proficiency levels), and **NarrativeTypes** (story frameworks).

This repository contains three baselines, all sharing the same three-focus structure:

- **Value** -- Business justification, financial management, and organizational alignment
- **Solution** -- Design, provisioning, optimization, and hosted items on the platform
- **Endeavor** -- Execution of the transformation: people, processes, and policies

---

## Platform Adoption Essentials

The root baseline for general platform transformations. Defines 13 Alphas with generic, domain-agnostic names (Platform, Requirements, Team, etc.), 21 ActivitySpaces, 8 Competencies, and 14 NarrativeTypes.

This is the baseline referenced by most practices in this repository.

![Platform Adoption Essentials -- Overview of Concerns](platform%20adoption%20essentials.png)

**File:** [`platform-adoption-essentials.json`](platform-adoption-essentials.json)

---

## IDP Essentials

A domain adaptation for **Internal Developer Platforms**. Extends the Platform Adoption Essentials structure with IDP-specific terminology aliases (e.g., Platform becomes "Internal Developer Platform", Requirements becomes "Developer Experience Needs", Platform Consumption Interface becomes "Developer Portal"). Adds developer-experience-focused ActivitySpaces (Curate Developer Experience, Manage Service Discovery, Secure Software Supply Chain, Measure Platform Adoption, Enable Platform Onboarding) and two additional Competencies (Product Management, Developer Experience Design).

![IDP Essentials -- Overview of Concerns](idp%20essentials.png)

**File:** [`idp-essentials.json`](idp-essentials.json)

---

## Infrastructure Automation Essentials

A domain adaptation for **Infrastructure as Code (IaC)** practices. Extends the core baseline with two new Alphas -- **Managed Asset** (representing infrastructure resources under automation control) and **Asset Governance** (lifecycle and compliance management for automated resources). Adds IaC-specific ActivitySpaces (Provision Managed Assets, Operate Managed Assets, Decommission Managed Assets, Assess Asset Governance Maturity, Enforce Asset Compliance, Enable Autonomous Operations) and uses vendor-agnostic terminology mapping (e.g., Platform becomes "Automation Platform", Platform Asset becomes "Automation Artifact").

![Infrastructure Automation Essentials -- Overview of Concerns](infrastructure%20automation%20essentials.png)

**File:** [`infrastructure-automation-essentials.json`](infrastructure-automation-essentials.json)
