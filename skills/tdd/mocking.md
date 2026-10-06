# Test doubles at external boundaries

Keep the project's internal collaborators real. Replace dependencies outside the system when needed for reliable, bounded tests: provider APIs, time, randomness, and sometimes filesystem or database access. Prefer an isolated test database when persistence semantics matter.

Pass external clients or clocks into the boundary rather than constructing them inside domain behavior. Prefer a client with named operations over a generic fetch mock containing a maze of endpoint conditions. Make fixtures represent relevant external contracts, including important errors.

Use the smallest double that preserves the behavior under test. A provider simulation proves how the application handles that simulated response; it does not establish provider consent, a live integration, or hosted readiness. Follow agreed environments and authorization for real external checks.

Adapted from [Matt Pocock's mocking guidance](https://github.com/mattpocock/skills/blob/main/skills/engineering/tdd/mocking.md).
