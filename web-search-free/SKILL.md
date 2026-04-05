---
name: web-search-free
description: Search the web for free using DuckDuckGo. Use when the user asks to search the web, look something up, find current information, or research a topic.
---

# Web Search Free

## Instructions

Call the `run_js` tool using `index.html` and a JSON string for `data` with the following fields:
- **query**: Required. A concise search query (3–8 words) extracted from the user's request. Remove conversational words and focus on the core topic (e.g., use "Eiffel Tower height" not "can you tell me how tall the Eiffel Tower is").

**Constraints:**
- Provide a concise summary (1-3 complete sentences) based on the result to conserve context. Always ensure your response ends with a finished sentence.
- Your response MUST BE written in the SAME language as the user's original prompt.
- If `result` is empty and only `searchURL` is returned, inform the user that no instant answer was found and provide the `searchURL` for manual search.
- For time-sensitive topics, include the current year in the query (e.g., "Germany chancellor 2026").
