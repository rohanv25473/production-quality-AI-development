# Behavior-focused tests

Exercise real internal code through the interface callers use. Choose meaningful scenarios from the approved behavior. Each test should establish one logical outcome; several assertions can describe that same outcome.

For example, test a public total-calculation function with two known inputs and assert the worked result, such as 15. Do not calculate the expected total using the same reduction as the implementation. For persistence, exercise the public create and retrieval operations together instead of checking an internal database row behind that interface.

Watch for tests that fail solely because an internal collaborator was renamed or reorganized. Private-method tests and internal call-count assertions usually describe construction rather than behavior. External interaction assertions can be appropriate when that interaction is the specified observable contract.

Cover important failure and boundary cases at the same public interface. For a defect, choose an input that demonstrates the wrong behavior and fails before the repair. Do not add tests merely to exercise every helper or satisfy an arbitrary assertion count.

Adapted from [Matt Pocock's test guidance](https://github.com/mattpocock/skills/blob/main/skills/engineering/tdd/tests.md).
