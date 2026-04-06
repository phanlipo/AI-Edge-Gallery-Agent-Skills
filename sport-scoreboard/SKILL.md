---
name: sport-scoreboard
description: Build a simple sport scoreboard (football, basketball, tennis, table-tennis) with compact markdown plus a webview card.
---

# Sport Scoreboard

## Instructions

Call the `run_js` tool using `index.html` and pass a JSON string in `data`.

Required fields:
- `sport`: `"football" | "basketball" | "tennis" | "table-tennis"`
- `scores`: sport-specific score object

Optional fields:
- `home`, `away`, `status`, `clock`

## Score formats

- **football**: `{ "home": number, "away": number }`
- **basketball**: `{ "home": number, "away": number, "period": "Q1|Q2|Q3|Q4|OT", "by_period": [{ "label": "Q1", "home": number, "away": number }] }`
- **tennis**: `{ "sets": [{ "home": number, "away": number }], "games": { "home": number, "away": number }, "points": { "home": "0|15|30|40|Ad", "away": "0|15|30|40|Ad" } }`
- **table-tennis**: `{ "sets": [{ "home": number, "away": number }], "current_set": number, "points": { "home": number, "away": number } }`

## Output

The script returns JSON containing:
- `headline`, `scoreline`, `details`, `markdown`
- `webview.url` pointing to `assets/webview.html`

## Response guidance

- Show `markdown` in chat.
- Keep text concise, because the card is rendered in webview.
- If `error` is returned, ask for corrected fields.
