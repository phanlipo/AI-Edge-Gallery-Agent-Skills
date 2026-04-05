---
name: true-random-dice
description: Roll one or more dice using local JavaScript cryptographic randomness. Use when the user asks to roll dice, generate random dice outcomes, or simulate tabletop rolls.
---

# True Random Dice

## Instructions

Call the `run_js` tool using `index.html` and a JSON string for `data` with the following fields:
- **count**: Optional. Number of dice to roll (default `1`, min `1`, max `100`).
- **sides**: Optional. Number of sides per die (default `6`, min `2`, max `1000`).
- **label**: Optional. A short context label, e.g., `"initiative"` or `"attack roll"`.

**Constraints:**
- Always show the list of rolled values and the total.
- If the tool returns `error`, apologize briefly and ask whether to retry.
