# 🧩 AI Edge Gallery – Self Skills

A collection of self-built Agent Skills for the [Google AI Edge Gallery](https://github.com/google-ai-edge/gallery) app.
Each skill extends on-device LLMs (like Gemma 4) with new capabilities — no cloud required.

---

## 📦 Available Skills

| Skill | Description | Type | API Key? |
|---|---|---|---|
| [`web-search-free`](./web-search-free/) | Web search via DuckDuckGo Instant Answer API | JavaScript | ❌ None |

> More skills coming soon.

---

## 🚀 How to Load a Skill

### Option A – Load from URL (recommended)

1. Open **Google AI Edge Gallery** on your device
2. Go to **Agent Skills → + → Load from URL**
3. Paste the raw URL of a `SKILL.md` file, e.g.:
   ```
   https://raw.githubusercontent.com/phanlipo/AI-Edge-Gallery-Agent-Skills/main/web-search-free/SKILL.md
   ```

### Option B – Load from local folder

1. Copy the skill folder (e.g. `web-search-free/`) onto your device
2. In the app: **Agent Skills → + → Load from folder**
3. Navigate to the skill folder and confirm

For the full official guide, see:
👉 [google-ai-edge/gallery – How to Add Skills](https://github.com/google-ai-edge/gallery/tree/main/skills#how-to-add-skills-in-the-gallery-app)

---

## 📁 Repository Structure

```
.
├── README.md
├── web-search-free/          # Free web search (DuckDuckGo)
│   ├── SKILL.md              # Skill metadata + LLM instructions
│   └── scripts/
│       └── index.html        # JavaScript logic (runs in WebView)
└── new-skill-name/           # New skills will be added here
    ├── SKILL.md
    └── scripts/
        └── index.html
```

Each skill lives in its own folder. The only required file is `SKILL.md`.
JavaScript skills additionally need `scripts/index.html`.

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
