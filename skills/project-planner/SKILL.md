---
name: project-planner
description: Turn approved product behavior into understandable technical plans and verifiable vertical increments, and maintain GitHub delivery tracking and acceptance evidence. Use for planning, dependency reviews, and progress reconciliation.
---

# Project planning

Use this skill in the main agent. The main agent owns planning, application changes and tests, tracking, and evidence reconciliation. Use a specialist only when a bounded task has a concrete expected benefit that justifies the handoff and usage; explain the benefit, define ownership and output, and assess the returned evidence. A separate planner is not required.

Follow the current repository's AGENTS.md and the owner's approved decisions. This reusable skill does not grant GitHub write authorization in a new repository or authorize implementation merely by creating tickets.

## Establish context

Read repository instructions, approved requirements, and relevant ADRs. Reconcile the configured live tracker; when the project uses GitHub, read its current Project, issues, milestones, and PRs. Discover destinations from existing configuration or remote metadata; ask only if a material choice cannot be discovered. Repository policy supplies work-item prefixes, status mappings, WIP limits, cost constraints, deferred scope, and approval boundaries. Do not carry one project's values or account details into another.

For a new project without a chosen planning destination, develop the proposed technical approach and increment breakdown in the conversation and agree the destination before publishing. Do not require an existing GitHub Project to plan or automatically create external trackers. When another tracker is established, apply the evidence, dependency, and approval principles using its supported features; GitHub-specific operations below apply only to projects using GitHub.

Keep new PRDs focused on what users see and how the product behaves. Technical choices and implementation planning belong in the planning activity after product approval. Existing governing specifications and ADRs remain authoritative; propose changes rather than silently amending product behavior.

GitHub is the live planning source of truth when the owner has adopted this workflow. Keep specifications, terminology, architecture decisions, and operating runbooks with the code. Do not generate parallel Markdown plans, phase reports, dependency registers, or issue checklists. If GitHub cannot be read, report the limitation and keep proposals in the conversation; do not infer current status from old notes or claim a write succeeded.

## Technical planning

Translate the approved outcome into a proportionate technical approach. Respect established architecture; revisit decisions only when the change warrants it. For consequential unresolved choices, explain the relevant alternatives, practical tradeoffs, risks, and recommendation. Cover interfaces, data changes, migrations, rollback, security, operations, or external setup where the approved scope actually requires them.

Present a concise decision summary the owner can understand as the person managing delivery: what is changing, why the approach fits, what choices need approval, and how success will be demonstrated. Put deeper detail needed for execution on the relevant issue or ADR. Avoid requiring the owner to understand file lists, implementation mechanics, or exhaustive technical designs to approve the direction.

Agree the appropriate verification approach: behaviors to check, relevant automated checks and environments, and the user scenario the owner will exercise. Leave detailed test implementation to execution. Reuse previously agreed testing boundaries; do not request approval again for routine choices within them.

Obtain owner approval of material architecture decisions and the initial increment plan before execution, unless that approval already exists. Small changes can use one concise review; consequential technical decisions may need review before finalizing the breakdown. Record unresolved decisions as proposals and their effect on readiness.

## Increment planning

Organize agreed scope as epics, features, and actionable leaf issues. Prefer narrow vertical slices delivering working behavior across the necessary layers that can be demonstrated and assessed independently. Separate foundational work only when it is a genuine prerequisite, with a concrete verifiable outcome. Use checkboxes for implementation subtasks unless independent ownership or acceptance warrants a separate issue.

Keep planning depth proportionate to the change and the owner's review needs. Map the approved scope, dependencies, and important risks clearly; detail approaching work enough for execution without overwhelming the owner or prescribing uncertain distant implementation. Revisit affected downstream work as evidence develops. Do not invent dates, estimates, decisions, reviews, or deployment evidence.

Each actionable issue needs a concrete outcome, bounded scope, testable acceptance criteria, dependencies, priority, and verification approach. For each substantial user-facing slice, include a before-and-after user test scenario: the existing behavior, intended improvement, steps the owner can exercise, and expected results. Planning defines the scenario; execution supplies the actual baseline, changed experience, and evidence. For foundational work, state its demonstrable effect and what it enables. Add estimates, component, value, risks, and milestone only when useful or required by the existing Project.

Preserve stable IDs and existing issue identities; reconcile existing work instead of creating duplicates. Use native parent/sub-issue and blocking relationships where available. Review the proposed granularity and sequencing with the owner before treating the initial plan as approved. Use continuous Kanban and existing fields and views; select the highest-priority unblocked agreed item within WIP and owner-review boundaries. Keep deferred work outside active execution and separate agent-executable work from genuine owner dependencies.

New scope, material priority changes, changed product behavior, and activation of deferred work remain proposals until approved. Routine sequencing and tracker maintenance within approved priorities do not require repeated permission.

## Execute and present a substantial slice

Start from the issue's outcome, acceptance criteria, prerequisites, relevant design references, and expected verification. Within an approved slice, implement, run agreed checks, fix failures, and prepare the review or PR without asking about routine implementation choices. Return to the owner if a decision materially changes approved scope, behavior, architecture, cost, or constraints. Respect repository authorization for commits, deployment, and merge.

Capture the observable baseline and its revision/environment before implementation. After a substantial slice, provide a before-and-after experience the owner can use and test, with access instructions, sample data where appropriate, repeatable steps, and expected results. Prefer safe local previews. When feasible, make both revisions runnable in isolated environments; otherwise provide a reproducible baseline comparison and state the limitation. Screenshots and recordings can supplement the user test. Label simulations and descriptions clearly, and distinguish them from real-provider acceptance. Do not fabricate a baseline or deploy/publish beyond existing authorization.

Report the resulting behavior, revision/PR, environment, checks and results, limitations, and any remaining owner dependencies. For foundational work without a user-facing change, present observable technical evidence and explain its practical effect. Keep acceptance evidence in the issue or PR, not a new local status report.

Ask for the owner's review and feedback. Do not treat the slice as owner-accepted or move to another substantial slice before that review unless the owner has explicitly authorized continuation. Owner feedback can confirm the result, request corrections within the slice, or change direction; record material scope changes as proposals. Routine corrections and verification within the approved slice remain agent work.

## Reconcile tracking and evidence

At implementation-session start, reconcile relevant live issues, PRs, blockers, and WIP before selecting ready work. After a substantial slice or a scope/dependency change, update the affected portion of the plan. Ordinary edits and conversational questions do not require a full backlog review.

Inspect actual changes and check results; the main agent's own summary or a specialist's report is not sufficient proof. Record revision, environment, checks, results, links, and material limitations on the affected issue or PR. Scale verification to the change and do not rerun expensive checks without a reason.

Maintain one tracker writer at a time. Re-read affected state immediately before updating it; preserve owner edits, discussion, and unrelated fields. Reconciliation with unchanged evidence should not create duplicate issues or comments. Prefer native automation and existing maintenance scripts, but verify their effects; item synchronization is not an acceptance review. If a mutation partially succeeds, inspect the state before retrying and report unresolved writes.

Treat code delivery, automated verification, owner review, real-provider/live acceptance, and release readiness as distinct gates. Close an issue or mark Done only when its acceptance criteria have evidence, including owner acceptance where required. A merged PR or passing tests alone cannot establish deployment or live acceptance. Implementation may complete while a separate live-acceptance item remains open. Roll up parents and milestones only when required child outcomes and their own criteria are satisfied.

Link PRs to issues. Use closing keywords only when merging fulfills every criterion; use references for partial work or outstanding acceptance. Respect review/merge policy; do not assert independent approval from self-authored review or check an owner's approval box. Preserve authorization boundaries for merges, releases, paid services, external messages, and unattended work.

## Report

Return affected GitHub links, evidence-backed status, the owner review or decision needed, and proposed next ready work. Describe genuine owner-only blockers with the precise action and what it unlocks. Do not repeatedly request previously recorded inputs while independent authorized work remains. State uncertainty, inaccessible evidence, and failed updates explicitly.

This skill runs during requested work sessions; it does not create an always-on agent or scheduled service. Its personal installation must be provisioned in a fresh environment.

Adapted from GitHub awesome-copilot's [breakdown-plan](https://github.com/github/awesome-copilot/tree/main/skills/breakdown-plan), revised for GitHub tracking and owner-reviewed incremental delivery.
