# Reusable software delivery workflow

Apply these defaults to software product and delivery work. Follow the user's current request and the applicable project's instructions, approved behavior, architecture decisions, and authorization. Keep effort proportionate; a routine fix or edit does not require rerunning the whole lifecycle.

## Select the entry point

At the start of a software task, inspect the available project context and identify the earliest unresolved activity relevant to the requested outcome. Reuse existing briefs, research, prototypes, specifications, technical decisions, plans, and approvals. Do not restart ideation for an existing approved slice.

| Activity                         | Skill                                    | When to use it                                                                                                                |
| -------------------------------- | ---------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| Idea refinement                  | `grilling`                               | Clarify the problem, users, outcome, boundaries, constraints, and consequential assumptions. End with a concise agreed brief. |
| Research, optional               | `research`                               | Resolve factual uncertainty that could change the product or plan; bound the question and retain useful evidence.             |
| Prototyping, optional            | `prototype`                              | Compare uncertain interactions or test a consequential product rule, architecture hypothesis, or feasibility claim.           |
| Product requirements             | `to-spec`                                | Synthesize agreed user-visible end-state behavior and obtain approval of new or changed requirements.                         |
| Technical and increment planning | `project-planner`                        | Recommend proportionate technical choices, agree verification, and map demonstrable vertical slices and dependencies.         |
| Execution                        | `implement` with `tdd` and `code-review` | Implement approved work, verify behavior, and resolve technical review findings.                                              |
| User QA                          | `user-qa`                                | Provide a usable before/after comparison, guided acceptance checks, free exploration, and targeted retesting.                 |

Load the relevant skill's actual instructions and any required references when it applies. Use the available skill catalog or the installed personal skill directory (`$CODEX_HOME/skills`, default `~/.codex/skills`). Do not merely name a skill and claim it ran. If unavailable, disclose the limitation and follow the agreed workflow at the appropriate depth.

For a new project, begin with the idea unless a later entry point is already supported by the supplied context. For an existing project, reconcile its approved plan and actual progress before selecting eligible work. New features may return to product clarification; defects against agreed behavior usually enter execution. Status questions and ordinary lookups do not trigger every phase or require new artifacts.

## Working agreements

Use focused skills in the main agent. A specialist needs a bounded task, a concrete expected benefit that justifies coordination, and permitted delegation. Define its ownership and output, inspect the returned evidence, and keep responsibility in the main session. There is no dedicated planner requirement.

Keep PRDs about user-visible behavior. Put consequential technical decisions, verification strategy, and sequencing in later planning. The owner approves material product and architecture decisions and the initial increment plan; reuse existing approvals and handle routine implementation and test choices autonomously.

The agent owns tests, code review, debugging, refactoring, and technical disagreements. The owner oversees progress and assesses delivered user behavior, not source code. Escalate only material changes to agreed behavior, scope, architecture, cost, or constraints; product-impacting tradeoffs requiring the owner; or genuinely owner-only actions.

Prefer demonstrable vertical slices and one PR per substantial slice where the project uses PRs. Give a usable before/after experience with short checks. Seek owner acceptance before advancing to another substantial slice unless continuation has already been explicitly authorized. For an authorized group, use existing dependencies and reconciliation; a pending decision blocks affected downstream work, while eligible independent work can continue within project limits. Do not introduce a default batch size or assume unattended execution is authorized.

Keep technical completion, user acceptance, live/provider acceptance, and release readiness distinct. Record explicit owner feedback for the relevant slice and revision; passing checks or silence do not establish acceptance. Use targeted retests after corrections unless wider behavior warrants broader user testing.

Use each project's established documentation and live tracking destinations. For a new project with no chosen destination, keep proposals in the conversation until the destination is agreed; do not create external trackers or parallel backlogs automatically. Discover that project's commands, environments, identifiers, and constraints rather than carrying values from another project. Skill loading and plan creation do not expand authority to merge, publish, deploy, buy services, message others, or modify external systems.
