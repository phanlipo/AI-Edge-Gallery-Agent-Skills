---
name: web-search-free
description: Search the web for free using DuckDuckGo. No API key required. Use when the user asks to search the web, look something up, find current information, news, or research any topic.
---

# Web Search Free (DuckDuckGo)

## Instructions

Call the `run_js` tool using `index.html` and a JSON string for `data` with the following fields:
- **query**: Required. A concise search query (3–8 words) extracted from the user's request. Remove conversational words and focus on the core topic (e.g., use "Berlin weather today" not "what is the weather like in Berlin today").

**Constraints:**
- Provide a concise summary (2-4 complete sentences) based on the returned results to conserve context. Always ensure your response ends with a finished sentence.
- Your response MUST BE written in the SAME language as the user's original prompt.
- Present the top results as a short list with title and URL if available.
- If `error` is returned, inform the user and suggest they search manually at https://duckduckgo.com.
- For time-sensitive topics, include the current year in the query (e.g., "Germany chancellor 2026").
