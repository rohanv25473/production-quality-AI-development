# Logic and state simulations

Prefer a self-contained HTML file that the owner can open without a build setup. State the product question visibly. Use domain vocabulary for actions, state, and explanations rather than requiring the owner to understand internal interfaces.

Keep the state model separate from the page controls. Choose the simplest reducer, state machine, or function set that expresses the question. Render meaningful fields and what changed after an action; a raw object dump alone is rarely enough for a user assessment.

Provide free-play controls and guided scenarios that reset to a known starting state. Include the normal journey, an important edge case, and a prohibited transition where relevant. Make the consequences of each action observable.

Keep everything in memory unless persistence is the question. Explain simulated assumptions and record what the owner learned or corrected. Any reuse of the logic in production still goes through technical planning and verification; the demo itself is an experiment.

Adapted from [Matt Pocock's logic prototype guidance](https://github.com/mattpocock/skills/blob/main/skills/engineering/prototype/LOGIC.md).
