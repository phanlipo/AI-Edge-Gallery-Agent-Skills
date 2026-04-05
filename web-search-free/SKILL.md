---
name: web-search-free
description: Searches the web for free using DuckDuckGo's Instant Answer API — no API key required. Use this skill when the user asks to search the web, look something up, find current information, research a topic, or needs facts beyond the model's training data. Trigger with "search for", "look up", "find information about", "what is", "who is", "latest news about", "current status of".
metadata:
  homepage: https://github.com/phanlipo/AI-Edge-Gallery-Agent-Skills/web-search-free
  version: 1.0.0
  author: Community
  tags: [search, web, duckduckgo, free, no-api-key]
  js-skill: true
---

# Web Search (Free – DuckDuckGo)

This skill performs a web search using the **DuckDuckGo Instant Answer API**.
No API key or account is required. All searches are free.

## How to use this skill

When the user asks a question that requires current web information, extract a
concise search query and call this skill.

## Parameters

Call the JavaScript skill with a JSON object containing:

```json
{
  "query": "the search query string"
}
```

## Instructions

1. Extract a short, focused search query (3–8 words) from the user's request.
2. Pass the query to the JavaScript skill via the `data` parameter.
3. The skill will return a JSON object with:
   - `result.answer` – direct answer (e.g. calculations, conversions)
   - `result.abstract` – Wikipedia-style summary
   - `result.abstractSource` – source name (e.g. "Wikipedia")
   - `result.abstractURL` – link to the full source
   - `result.relatedTopics` – array of related result titles and URLs
   - `result.searchURL` – fallback DuckDuckGo search URL
4. Present the information clearly to the user.
5. If `answer` and `abstract` are both empty, inform the user that no instant
   answer was found and provide the `searchURL` for them to search manually.

## Example

User: "Was ist die Hauptstadt von Australien?"
Query: `"capital of Australia"`

User: "Neueste Nachrichten zu KI"
Query: `"artificial intelligence news 2026"`
