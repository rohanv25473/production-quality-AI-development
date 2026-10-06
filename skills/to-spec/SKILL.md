---
name: to-spec
description: Synthesize agreed ideas and findings into a behavior-only product requirements document for owner approval. Use to write or refine a PRD or product spec; architecture, implementation sequencing, and test mechanics belong to later planning.
---

# Describe the product end state

Synthesize what the conversation, approved brief, research, and prototypes have established. Reuse the project's domain vocabulary and governing decisions. Inspect existing product behavior where relevant, but do not restart a settled interview or silently rewrite an approved specification.

If a consequential product question remains unresolved, use `grilling` for that question before claiming the PRD is ready. Keep assumptions and unresolved decisions visible rather than turning them into invented requirements. When the inputs are sufficient, write the document without another interview.

## Keep the content about behavior

Describe what users see, what they can do, and how the product responds. Explain the intended end state rather than the implementation journey. Include product constraints that affect the experience; preserve previously agreed constraints without inventing quantitative targets.

Scale the document to the task: a new product may need a full PRD, a feature a scoped behavior specification, and a fix concise acceptance criteria. Use only the sections that make the agreed outcome understandable:

- Problem, intended users, and desired outcomes.
- Capabilities, user journeys, and relevant product rules.
- Observable success, empty, error, and boundary behavior.
- User-facing acceptance criteria and important product constraints.
- Explicit scope boundaries and unresolved product decisions.

User stories can clarify capabilities, but do not generate an exhaustive speculative list. Keep acceptance criteria observable and assessable by a user. They may describe scenarios and expected results; they do not specify test libraries or internal testing boundaries.

Leave architecture, modules, database schemas, internal API contracts, test strategy, file lists, estimates, dependencies, tickets, and implementation sequencing to `project-planner`. Translate prototype findings into product behavior rather than embedding prototype source code. Existing ADRs remain governing context, not a reason to add an implementation section to the PRD.

## Review and retain

Present a draft and identify any material product decisions requiring approval. An existing approval of unchanged behavior can be reused; do not manufacture an extra approval gate for routine wording. Obtain approval of new or changed product behavior before treating it as the authoritative specification or ready for execution planning.

Use the project's established specification destination and external-write authorization. An explicitly requested file can be saved as a labeled draft before approval. Do not automatically publish to a tracker, apply readiness labels, overwrite governing requirements, or require Matt's setup skill. Without a configured destination, present the draft in the conversation and settle its durable location before saving it.

After product approval, hand the approved behavior and remaining factual limits to `project-planner` for technical and vertical-increment planning. PRD approval alone does not authorize implementation or a material technical choice.

Adapted from [Matt Pocock's to-spec skill](https://github.com/mattpocock/skills/blob/main/skills/engineering/to-spec/SKILL.md), with implementation and testing planning kept in the later planning phase. Upstream license is included in `LICENSE`.
