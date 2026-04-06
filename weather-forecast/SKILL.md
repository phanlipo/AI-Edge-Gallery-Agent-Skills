---
name: weather-forecast
description: Get a weather forecast for a location using Open-Meteo geocoding and forecast APIs. Use when the user asks for weather outlook, forecast, temperature ranges, or rain chances for a place.
---

# Weather Forecast

## Instructions

Call the `run_js` tool using `index.html` and a JSON string for `data` with the following fields:
- **location**: Required. City, region, or place name (e.g., `"Berlin"`, `"Munich, DE"`).
- **days**: Optional. Forecast days (default `3`, min `1`, max `7`).
- **units**: Optional. `"metric"` (default, Celsius) or `"imperial"` (Fahrenheit).

The script returns:
- Resolved location details (`name`, `country`, coordinates, timezone)
- Daily forecast list including max/min temperature, precipitation sum, and max wind speed
- Current weather snapshot (if available)

**Response guidance:**
- Summarize the forecast day-by-day with date, high/low, and precipitation.
- If `error` is returned, apologize briefly and ask whether to retry with a more specific location.
