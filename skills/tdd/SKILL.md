---
name: tdd
description: Implement features or fixes through one failing behavior test and one minimal implementation at a time. Use for test-first development at agreed public testing boundaries and for choosing behavior-focused tests or external test doubles.
---

# Test-driven development

Keep Matt's red-to-green loop: test one behavior, make it work, then repeat. Refactoring belongs to the review stage, followed by relevant verification. These small test cycles are internal agent work, not owner-reviewed delivery increments.

Read the project's existing domain glossary and relevant architecture decisions. Discover their actual locations from repository instructions; do not require a new `GLOSSARY.md` or a separate architecture skill.

## Testing boundaries

A testing boundary is a public interface through which a caller observes behavior without reaching into implementation details. Reuse the behavior and testing boundaries agreed during technical planning. Select routine fixtures, assertions, and test-file placement yourself; do not ask for approval of individual tests.

If there is no agreed verification approach, establish a proportionate behavior and boundary proposal through planning. Use existing interfaces and architecture to resolve ordinary uncertainty. Escalate only a consequential change to the approved approach, rather than introducing an unconfirmed architecture or requiring the owner to design tests.

Read [tests.md](tests.md) when designing tests and [mocking.md](mocking.md) when choosing test doubles. Test observable behavior using real internal code. Prefer known expected results from the requirements, a worked example, or another independent source. Do not repeat the implementation inside the assertion, test private methods, or couple tests to internal call order.

## Red to green

1. Choose one required behavior at an agreed boundary. Write its test first.
2. Run that test and observe it fail because the behavior is missing or wrong. Resolve setup, syntax, and environment failures before treating the result as the red step.
3. Add only enough implementation to pass. Avoid speculative features or abstractions.
4. Run the focused test, then move to the next behavior. Run type checks and nearby regression tests as needed.

Do not write a large batch of imagined tests followed by a large batch of implementation. Fixes found during review should gain a reproducing behavior test where practical. Keep in-scope cleanup in review rather than inserting a separate refactoring stage into every red-to-green cycle.

Use TDD where practical. For work poorly suited to test-first development, explain the reason and verify it appropriately through existing tests, a build, a targeted integration check, or a reproducible user check. This is not permission to omit required checks. New tests should protect meaningful behavior rather than mirror reversible, low-impact edits.

Record which checks actually ran and any limits; simulated external responses do not establish real-provider acceptance. Follow repository approval and environment boundaries throughout.

Adapted from [Matt Pocock's TDD skill](https://github.com/mattpocock/skills/blob/main/skills/engineering/tdd/SKILL.md); upstream license is included in `LICENSE`.
