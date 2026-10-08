# Production Quality AI Development

A reusable software delivery workflow for Codex: focused skills guide the main agent, while you lead product decisions and assess working results.

Adapted for owner-readable planning, demonstrable vertical slices, and minimal intervention in technical work. These instructions guide delivery; they do not guarantee production readiness on their own.

## The workflow

| Activity                               | Skill                                                                                                          | Result                                                                                           |
| -------------------------------------- | -------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------ |
| Refine the idea                        | [grilling](skills/grilling/SKILL.md)                                                                           | An agreed brief covering the problem, users, outcome, boundaries, and consequential assumptions. |
| Research, when needed                  | [research](skills/research/SKILL.md)                                                                           | Bounded findings supported by primary sources and their implications for decisions.              |
| Prototype, when needed                 | [prototype](skills/prototype/SKILL.md)                                                                         | Evidence that resolves an uncertain interaction, product rule, or technical hypothesis.          |
| Define product requirements            | [to-spec](skills/to-spec/SKILL.md)                                                                             | An approved PRD describing user-visible end-state behavior.                                      |
| Plan technical delivery and increments | [project-planner](skills/project-planner/SKILL.md)                                                             | Proportionate technical decisions, verification, vertical slices, and dependencies.              |
| Implement and verify                   | [implement](skills/implement/SKILL.md), [tdd](skills/tdd/SKILL.md), [code-review](skills/code-review/SKILL.md) | Working approved behavior, meaningful checks, and resolved technical review findings.            |
| Assess the user experience             | [user-qa](skills/user-qa/SKILL.md)                                                                             | Usable before/after comparisons, short acceptance checks, feedback, and targeted retesting.      |

Research and prototyping are optional. Start at the earliest unresolved activity relevant to the task. Existing projects reuse their approved requirements, architecture, plan, and evidence; routine fixes do not restart the whole lifecycle.

## Your role and the agent's role

You approve material product and architecture decisions and the initial increment plan. You oversee progress and test delivered user behavior through before/after comparisons.

The agent owns implementation, tests, code review, debugging, refactoring, and routine technical corrections. It escalates material changes to agreed scope, behavior, architecture, cost, or constraints, product-impacting tradeoffs requiring your decision, and actions only you can perform.

The main agent uses focused skills. No dedicated planner agent is required. A specialist is useful only when a bounded task has a concrete benefit that justifies the coordination and delegation is permitted.

By default, substantial slices return for your acceptance before the next one begins. You can explicitly authorize a group of eligible slices and review them together afterward. Existing dependency mapping determines what can continue: a pending decision blocks affected downstream work, while independent authorized work can proceed within project limits. There is no fixed batch size or automatic unattended execution.

Technical completion, your acceptance, live/provider acceptance, and release readiness remain separate. Passing tests alone does not establish all four.

## Install once, reuse across projects

This repository contains shared [AGENTS.md instructions](AGENTS.md) and nine skill folders with their supporting references and license notices. It contains no dedicated agent configuration or running service.

1. Clone this repository, or download its files.
2. Copy all nine folders from `skills/`, including their references and licenses, into the personal skill directory supported by your Codex environment. The original installation uses `~/.codex/skills`; current official documentation also describes `~/.agents/skills` for user discovery. Use one discoverable copy of each skill, preserving unrelated installed skills.
3. Merge this repository's `AGENTS.md` into your global Codex instructions, normally `~/.codex/AGENTS.md`, or the equivalent file under your configured `CODEX_HOME`. Preserve existing guidance. Repository-specific instructions continue to supply project rules and constraints.
4. Start a fresh Codex session. Confirm the shared instructions and all nine skill names are available. If automatic discovery is unavailable, make the files accessible and explicitly instruct the agent to load the relevant skill.

Official references: [global and project instructions](https://learn.chatgpt.com/docs/agent-configuration/agents-md) and [skill discovery](https://learn.chatgpt.com/docs/build-skills).

The files in this repository are the versioned source. Installed copies are separate: pull and review updates before copying changed files into your personal installation. Installation does not configure automatic updates.

Each project retains its own requirements, architecture, tracking destination, commands, environments, budget, and permissions. Loading a skill or creating a plan does not authorize publishing, deploying, merging, buying services, messaging others, or unattended execution. For a new project without a chosen tracker, planning proposals stay in the conversation until a destination is agreed.

## Example requests

- New project: "Use my delivery workflow to grill me about this product idea."
- Product requirements: "Turn our agreed brief and findings into a behavior-only PRD. Keep implementation planning for later."
- Technical planning: "Use project-planner to recommend an understandable technical approach and demonstrable vertical slices for this approved PRD."
- Existing project: "Reconcile our approved plan with actual progress and identify the next eligible slice."
- Authorized execution: "Implement this approved slice using implement, tdd, and code-review, then give me a usable before/after handoff."
- Group selection: "Using the plan, identify the next independent vertical slices I could authorize together." Approve the specific group separately before execution.

Natural requests are sufficient when the shared instructions are loaded. You may also invoke a skill explicitly, for example `$project-planner` or `$implement`.

## Credits and license

See [ATTRIBUTIONS.md](ATTRIBUTIONS.md) for upstream sources and adaptations. Original contributions are provided under the [MIT license](LICENSE). Adapted skills retain their upstream MIT notices in their own folders.
