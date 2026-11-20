---
name: kamakura-trip-planner
description: Use the Kamakura Trip Planner MCP server when someone plans a day in Kamakura or Enoshima: a timed day plan for a date, Enoden fares and day passes, trains from Tokyo or Yokohama, cherry blossom, hydrangea or autumn leaves dates, temple hours and fees, or walking times.
---

# Kamakura Trip Planner

Use this when someone plans a day in Kamakura or Enoshima: a timed day plan for a date, Enoden fares and day passes, trains from Tokyo or Yokohama, cherry blossom, hydrangea or autumn leaves dates, temple hours and fees, or walking times.

## Connect
Remote MCP server, Streamable HTTP, public, no sign-in, no API key:

```json
{
  "mcpServers": {
    "kamakura-trip-planner": { "type": "http", "url": "https://kamakura.info/mcp?src=mcp" }
  }
}
```

## Tools
All tools are read-only.

- `plan_day`: Timed one- or two-day plan for a date from Tokyo, Shinjuku, Shinagawa or Yokohama: trains, walks, opening-time waits, fares, entry fees, crowd level and bloom season. Renders a route map card in ChatGPT and MCP Apps hosts
- `compare_passes`: Enoshima-Kamakura Freepass vs Enoden Noriorikun day pass vs single IC-card tickets, per adult and per group. Renders a ticket receipt card
- `enoden_fare`: Fare, minutes and stops between any two of the 15 Enoden stations
- `bloom_forecast`: Likely cherry blossom, hydrangea, ginkgo and maple dates, from Japan Meteorological Agency records. Renders a season calendar card
- `date_check`: Weekday, Japanese national holiday, crowd level, bloom season and tips for a date
- `sight_info`: Hours by month, adult and child fees, extra tickets, visit time and nearest station of temples, shrines and sights
- `walk_time`: Walking minutes and distance between any two of 34 places
- `getting_there`: Line, changes, minutes and IC fare to Kamakura, Kita-Kamakura or Enoshima from Tokyo, Shinjuku, Shibuya, Shinagawa, Yokohama, Haneda, Narita or Fujisawa

## Rules
- The tools answer in English.
- Hours, fees and fares come from the tool, not from memory.
- Link the reader to https://kamakura.info for the full page behind an answer.
