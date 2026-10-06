---
name: user-qa
description: Prepare usable before-and-after demonstrations and short acceptance checks for substantial slices, then handle owner feedback and targeted retesting. Use for user-experience handoffs; automated checks and agent review do not substitute for the owner's acceptance.
---

# User acceptance handoff

The owner manages progress and assesses user-visible behavior. The agent owns code review, tests, debugging, and routine technical corrections. Follow the repository's evidence locations, owner-review boundaries, and existing authorization.

## Prepare the comparison

Start from the planned before/after user scenario and acceptance criteria. Before implementation, capture the actual baseline revision, environment, and observable behavior. After implementation, identify the changed revision and verify that the described experience is accessible.

Prefer safe local previews. When feasible, make both revisions runnable in isolated environments with suitable sample data. Otherwise give a reproducible baseline comparison and explain its limitation. Protect existing data and owner edits; do not reset environments or deploy beyond authorization. Screenshots or recordings may supplement the experience, but do not present them as a runnable comparison. Label simulations and distinguish them from real-provider acceptance.

Present the changed outcome, access instructions, a short checklist tied to acceptance criteria, expected results, and meaningful verification limits. Keep setup instructions actionable for a user rather than requiring source-code inspection. The agent performs environment preparation it can do; ask for genuinely owner-only access or actions precisely.

Invite free exploration after the guided checks. At a feature or milestone boundary, include the relevant critical end-to-end journeys. For foundational work, provide agent-verified technical evidence and explain its practical effect without requiring the owner to review code.

## Handle feedback

Classify failures against agreed behavior as corrections to the existing slice. The agent reproduces them, fixes them, resolves technical review findings, and reruns relevant checks. New preferences, improvements outside scope, or changed requirements return to planning as proposals. Ask for clarification only when ambiguous feedback affects the intended behavior and cannot be resolved from existing decisions.

After correction, provide a short targeted retest of affected behavior. Request broader user testing only when the change affects other interactions or a critical end-to-end journey; explain which additional behavior needs checking. Do not make the owner repeat unchanged checks routinely.

## Record acceptance

Record actual owner feedback and evidence on the issue or PR. Require an explicit acceptance signal for the identified slice and revision; silence, passing tests, and agent agreement do not establish owner acceptance. Feedback or approval for an older revision is not automatically evidence for materially changed behavior.

A group may be reviewed together while acceptance remains per slice. Reconcile the accepted and unaccepted work separately through `project-planner`. Respect existing continuation authorization and dependency limits without introducing a default batch size or automatic continuation policy. Merge, provider acceptance, and release gates remain governed by repository instructions.

If `project-planner` is unavailable, disclose the limitation and reconcile evidence and next work against the existing approved plan and repository tracking rules. Do not claim the skill ran or create a replacement backlog.
