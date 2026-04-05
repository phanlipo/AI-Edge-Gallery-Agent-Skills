# Skill Authoring Guide (AI Edge Gallery)

This document explains how new skills should be structured in this repository.

## Which format is correct?

- **For AI Edge Gallery skills**: use one folder per skill with `SKILL.md` + `scripts/index.html`.
- **`AGENTS.md`** is primarily for agent/development workflow instructions in the repo, **not** the standard format for Gallery skill definitions.

## Standard structure per skill

```text
<skill-name>/
├── SKILL.md
└── scripts/
    └── index.html
```

## 1) Writing `SKILL.md`

Every skill needs frontmatter:

```yaml
---
name: my-skill-name
description: Short description of when this skill should be used.
---
```

Then add:
- a short title,
- clear tool instructions (typically: `run_js` with `index.html`),
- input fields (`data` JSON) with type/default/bounds,
- output constraints (for example language, brevity, error behavior).

## 2) Writing `scripts/index.html`

Recommendations:
- Expose `window["ai_edge_gallery_get_result"] = async (data) => { ... }`.
- Parse `data` defensively (`JSON.parse(data || "{}")`).
- Validate/clamp inputs.
- Always return a **JSON string** (`JSON.stringify(...)`).
- On failures, return `{ error: "..." }`.

## 3) Hosting requirements (important)

JavaScript skills should be served from proper web hosting (for example GitHub Pages or Cloudflare Pages) so files are delivered with compatible headers/MIME types.

For GitHub Pages:
- Add a **`.nojekyll`** file at the repository root (already present here).
- This keeps `SKILL.md` served as-is and prevents Jekyll transformations.

## 4) Quality checklist before commit

- [ ] Skill folder name and `name` in `SKILL.md` match.
- [ ] `SKILL.md` clearly defines inputs/constraints.
- [ ] `index.html` exports `ai_edge_gallery_get_result`.
- [ ] Responses are always valid JSON strings.
- [ ] Error paths return `{ error: ... }`.
- [ ] README is updated (skill list + example URL + structure).
- [ ] `git diff --check` is clean.

## 5) Optional: quick smoke tests

For local validation, you can eval the `<script>` block from `index.html` in Node
(with `global.window={}` and `global.crypto=require('crypto').webcrypto` if needed),
then call `window.ai_edge_gallery_get_result(...)`.
