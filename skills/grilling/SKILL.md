---
name: grilling
description: Refine and stress-test an idea, plan, or decision through structured question rounds with recommendations. Use when shaping a product idea, stress-testing a proposal, or the user asks to be grilled.
---

Interview the user relentlessly until you reach a shared understanding. Map this as a **design tree**: every decision branches into the decisions that hang off it.

Keep the tree focused on consequential decisions relevant to the agreed outcome and desired depth. Reuse settled choices; do not explore unrelated possibilities or require technical detail beyond what the user's decision needs.

Work the tree in **rounds**. The **frontier** is every relevant consequential decision whose prerequisites are already settled: the questions you can ask _now_ without guessing at answers you haven't heard yet. Ask the whole frontier in one round: number each question and give your recommended answer. Then wait for the user's answers before the next round.

Format a round like so:

```
❓ **Q1** - **<question title>**: <question body, might be multiple paragraphs, including multiple choices>

➡️ <your recommended answer>

---

❓ **Q2** - **<question title>**: <question body, might be multiple paragraphs, including multiple choices>

➡️ <your recommended answer>
```

Each round the user answers reshapes the tree: settled decisions push the frontier outward and unblock questions that depended on them. Recompute the frontier and ask the next round. A question whose answer depends on another question still open in this round belongs to a _later_ round, not this one.

Finding _facts_ is your job, never the user's. When a frontier question needs a fact from the environment (filesystem, tools, etc.), investigate it yourself; don't ask the user for anything you could look up. Delegate a bounded lookup only when its concrete benefit justifies the handoff and delegation is permitted. Don't block unrelated questions on research: a running exploration is an unsettled prerequisite, so only the questions downstream of it wait for the findings; ask the rest of the frontier now. The _decisions_ are the user's: put each to them and wait.

The session is done when the relevant frontier is empty: the consequential decisions needed for the agreed outcome are settled, with assumptions and deferred questions explicit. Do not make hypothetical future branches prerequisites for finishing. For a software idea, finish with a concise brief of the problem, users, outcome, boundaries, constraints, and remaining uncertainties. Do not act on it until the user confirms you have reached a shared understanding.

Adapted from Matt Pocock's [grilling](https://github.com/mattpocock/skills/tree/main/skills/productivity/grilling) skill. See [LICENSE](LICENSE) for the retained upstream MIT notice.
