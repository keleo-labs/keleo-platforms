# Practices

Practice files extend a baseline with domain-specific Alphas, Activities, WorkProducts, Personas, Patterns, and Narratives. Each practice references its baseline by name via `baselinePracticeName` and can declare dependencies on other practices via `practiceDependencyNames`.

---

## Team Structure & Cognitive Load

Models team design through the lens of **Team Topologies** -- four fundamental team types (Stream-Aligned, Platform, Enabling, Complicated-Subsystem) and three interaction modes (Collaboration, X-as-a-Service, Facilitating). Introduces three new Alphas:

- **Cognitive Load** -- tracks mental bandwidth across intrinsic, extraneous, and germane dimensions
- **Team Topology Design** -- captures the intentional structure of teams for fast flow
- **Team Interaction Mode** -- models how teams collaborate and evolve boundaries

Defines four Personas (Organizational Designer, Stream-Aligned Team Lead, Platform Team Lead, Enabling Team Coach) organized into Executive Leadership, Platform Team, Stream-Aligned Team, and Enabling Team groups.

**Baseline:** Platform Adoption Essentials | **File:** [`team-structure--cognitive-load.json`](team-structure--cognitive-load.json)

---

## Organizational Evolution & Sensing

Focuses on continuous organizational adaptation through sensing mechanisms and the platform-as-product approach. Introduces the **Organizational Sensing** Alpha for tracking how organizations detect and respond to signals that indicate topology changes are needed.

Defines two Activities -- Establish Organizational Sensing and Build Thinnest Viable Platform -- performed by Leadership Team and Platform Team persona groups.

**Baseline:** Platform Adoption Essentials | **File:** [`organizational-evolution--sensing.json`](organizational-evolution--sensing.json)

---

## Team Topologies Lifecycle

An orchestration practice that coordinates the two practices above into a unified lifecycle. Declares `practiceDependencyNames` on both Team Structure & Cognitive Load and Organizational Evolution & Sensing. Provides `practiceElementAliases` that unify Team Topologies terminology (e.g., TVP/Thinnest Viable Platform maps to Platform, Topology maps to Team).

This practice contains no new Alphas, Activities, or Personas of its own -- its value is in the lifecycle patterns and terminology mapping that tie the two domain practices together.

**Baseline:** Platform Adoption Essentials | **Dependencies:** Team Structure & Cognitive Load, Organizational Evolution & Sensing | **File:** [`team-topologies-lifecycle.json`](team-topologies-lifecycle.json)

---

## Platform Engineering (CNCF)

Referenced by the [Platform Engineering method](../methods/platform-engineering.json) but the practice JSON is maintained externally. The concern diagram below shows the Alphas it contributes when composed into the Platform Engineering method, including Platform Product Management, Platform Investment Model, Capability Domain, Platform Measurement Practice, and Platform Adoption Journey.

![Platform Engineering (CNCF) -- Overview of Concerns](platform%20engineering%20(CNCF).png)
