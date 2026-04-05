# 🧩 AI Edge Gallery – Self Skills

A collection of self-built Agent Skills for the [Google AI Edge Gallery](https://github.com/google-ai-edge/gallery) app.
Each skill extends on-device LLMs (like Gemma 4) with new capabilities — no cloud required.

---

## 📦 Available Skills

| Skill | Description | Type | API Key? |
|---|---|---|---|
| [`web-search-free`](./web-search-free/) | Web search via DuckDuckGo Instant Answer API | JavaScript | ❌ None |
| [`true-random-dice`](./true-random-dice/) | Roll one or more dice with local JavaScript cryptographic randomness | JavaScript | ❌ None |

> More skills coming soon.

---

## 🚀 How to Load a Skill

### Option A – Load from URL (recommended)

1. Open **Google AI Edge Gallery** on your device
2. Go to **Agent Skills → + → Load from URL**
3. Paste the raw URL of a `SKILL.md` file, e.g.:
   ```
   https://phanlipo.github.io/AI-Edge-Gallery-Agent-Skills/web-search-free/SKILL.md
   ```

### Option B – Load from local folder

1. Copy the skill folder (e.g. `web-search-free/`) onto your device
2. In the app: **Agent Skills → + → Load from folder**
3. Navigate to the skill folder and confirm

For the full official guide, see:
👉 [google-ai-edge/gallery – How to Add Skills](https://github.com/google-ai-edge/gallery/tree/main/skills#how-to-add-skills-in-the-gallery-app)

### ⚠️ Hosting requirement for JS skills

To avoid WebView loading issues, host skill assets on a real web host (for example GitHub Pages or Cloudflare Pages). Standard GitHub repository URLs and `raw.githubusercontent.com` may be served with MIME types that can break JS skill execution in the app.

### Tip for GitHub Pages + `SKILL.md`

GitHub Pages enables Jekyll by default, which can transform Markdown files. Because AI Edge Gallery must fetch the raw `SKILL.md` content, keep a `.nojekyll` file in the repository root so `SKILL.md` is served as-is.

---

## 📁 Repository Structure

```
.
├── README.md
├── web-search-free/          # Free web search (DuckDuckGo)
│   ├── SKILL.md
│   └── scripts/
│       └── index.html
├── true-random-dice/         # Dice rolling with local JS randomness
│   ├── SKILL.md
│   └── scripts/
│       └── index.html
└── new-skill-name/           # New skills can be added here
    ├── SKILL.md
    └── scripts/
        └── index.html
```

Each skill lives in its own folder. The only required file is `SKILL.md`.
JavaScript skills additionally need `scripts/index.html` as the webview entry point for `run_js`.

### 🧭 Skill documentation for maintainers

A practical guide for writing new skills is available in [`SKILL_AUTHORING.md`](./SKILL_AUTHORING.md).

---

## ⚠️ Disclaimer

> **This repository is an independent community project and is not affiliated with, endorsed by, or officially connected to Google or the Google AI Edge team in any way.**
>
> The skills provided here are contributed on a best-effort basis.
> They are **not** guaranteed to be accurate, up-to-date, secure, or suitable for any particular purpose. Use them at your own risk.
>
> For official skills and documentation, refer to the [google-ai-edge/gallery repository](https://github.com/google-ai-edge/gallery/tree/main/skills).
>
> All product names, trademarks, and APIs referenced (including DuckDuckGo, Google, Gemma) remain the property of their respective owners.

---

## 📄 License

This repository is released under the [MIT License](./LICENSE).  
Individual skills may carry their own licenses — check each skill folder.
