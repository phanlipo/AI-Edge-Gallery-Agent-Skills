---
name: simple-calculator
description: Solve simple calculator tasks locally with JavaScript, including basic arithmetic (+, -, *, /) and square roots. Use when the user asks questions like "Was ist 5*10?", "What is 12 / 3?", or "Was ist die Wurzel von 9?".
---

# Simple Calculator

## Instructions

Call the `run_js` tool using `index.html` and pass a JSON string in `data` with one of the following inputs:

- **expression**: String with an arithmetic expression (supports numbers, spaces, `+`, `-`, `*`, `/`, `(`, `)`, `.`).
  - Examples: `"5*10"`, `"(12 + 8) / 4"`
- **sqrt**: Number for square-root calculation.
  - Example: `9`

If both are provided, prefer `expression`.

The script returns JSON with:
- `operation`: `"expression"` or `"sqrt"`
- `input`: normalized input value
- `result`: numeric result

Response guidance:
- Show the computed result clearly.
- If `error` is returned, apologize briefly and ask whether to retry with a simpler input.
