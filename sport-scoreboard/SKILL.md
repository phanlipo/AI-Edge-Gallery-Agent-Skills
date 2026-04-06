---
name: sport-scoreboard
description: Build and update an interactive scoreboard for football (soccer), tennis, table tennis, and basketball using local JavaScript. Use when the user asks to create, refresh, or display live/match scoreboards across these sports, including team/player names, period/set/game scores, match status, and clock/time context.
---

# Sport Scoreboard

## Instructions

Call the `run_js` tool using `scripts/index.html` and pass a JSON string in `data`.

### Input schema

- `sport` (required): one of `"football"`, `"basketball"`, `"tennis"`, `"table-tennis"`
- `home` (optional): display name for home team/player
- `away` (optional): display name for away team/player
- `status` (optional): free text like `"Live"`, `"Halftime"`, `"Final"`, `"In Progress"`
- `clock` (optional): free text like `"67:12"`, `"Q3 04:18"`
- `scores` (required): sport-specific object

### Sport-specific `scores`

- **football**: `{ "home": number, "away": number }`
- **basketball**: `{ "home": number, "away": number, "period": "Q1|Q2|Q3|Q4|OT", "by_period": [{ "label": "Q1", "home": number, "away": number }] }`
- **tennis**: `{ "sets": [{ "home": number, "away": number }], "games": { "home": number, "away": number }, "points": { "home": "0|15|30|40|Ad", "away": "0|15|30|40|Ad" } }`
- **table-tennis**: `{ "sets": [{ "home": number, "away": number }], "current_set": number, "points": { "home": number, "away": number } }`

## Output behavior

The script returns JSON with:

- `result` (short success text)
- `sport`, `home`, `away`, `status`, `clock`
- `headline` (single-line match headline)
- `scoreline` (main score)
- `details` (array of sport-specific lines)
- `markdown` (multi-line formatted scoreboard for direct chat output)
- `webview` (inline UI rendered by the app), with:
  - `url` (relative asset path, for example `webview.html?...`)
  - `aspectRatio` (number)

## Response guidance

- Show the returned `markdown` in chat.
- Keep the response concise because the app also shows the interactive `webview` inline.
- If the user asks for updates, rerun with changed values and show the refreshed board.
- If `error` is returned, apologize briefly and ask for the missing or invalid field.
