---
name: prototype
description: Build a temporary UI, logic, or technical experiment to resolve a consequential design or feasibility question. Use for comparing interactions or testing an uncertain hypothesis; a prototype verdict does not authorize production implementation.
---

# Prototype to make a decision

Prototyping is optional. Build an experiment only when experiencing an interaction or measuring a technical claim will resolve uncertainty better than discussion or research alone. Follow the current project's scope, conventions, permissions, and constraints.

## Choose the experiment

State the question, meaningful alternatives or hypothesis, and what observation would allow a decision. Use enough realism to assess that question without building the entire feature. Reuse prior answers; ask only about a consequential ambiguity that cannot be resolved from the current brief.

- For uncertain presentation or interaction, read [UI.md](UI.md) and provide two or three meaningfully different options when comparison is useful.
- For uncertain product rules or state transitions, read [LOGIC.md](LOGIC.md) and provide a small user-drivable simulation.
- For architecture or feasibility, isolate one claim and run a narrow experiment with appropriate measurements, representative inputs, and stated environmental limits. A technical experiment can use real components when they are necessary to test the claim and authorized.

The main agent normally builds the experiment. Specialist help requires a bounded concrete benefit and permitted delegation; it is not a mandatory design tournament.

## Build only what answers the question

Label the work as a temporary prototype. Use an isolated checkout, experiment branch, or permitted scratch location; preserve existing owner edits. In an existing application, follow its conventions and use surrounding context where helpful without replacing approved production behavior.

Make the experiment easy to run and inspect. Use in-memory state and representative sample data by default. Use isolated local persistence only when persistence itself is under examination. Do not wire exploratory UI actions to real mutations or publish/deploy beyond authorization. Show relevant state or measured results in language the owner can assess.

Skip production polish, speculative abstractions, and production test-suite work. Exercise the scenarios or measurements necessary to establish the experiment's result; an experiment that does not run cannot answer its question. Clearly state which parts are simulated. Avoid treating a mock as proof of feasibility for the component it replaces.

## Capture the verdict

Provide access instructions, relevant walkthroughs or measurements, tradeoffs, and limitations. Ask for the owner's interaction/design judgment where needed; report factual technical outcomes without asking the owner to inspect source code.

Retain the question, verdict, and reproducible artifact or branch reference in the project's permitted destination. With no authorized tracker or archive convention, keep the findings in the conversation and explain where the local artifact is. Do not automatically create tracker items or merge an experiment.

Carry the validated learning into the product brief or later technical planning as appropriate. Production work must follow the approved PRD and increment plan, then use `implement`, verification, and user QA. Prototype selection is not production acceptance, and prototype code is not automatically ready to ship.

Adapted from [Matt Pocock's prototype skill](https://github.com/mattpocock/skills/blob/main/skills/engineering/prototype/SKILL.md); upstream license is included in `LICENSE`.
