# Kamakura Trip Planner MCP

Kamakura and Enoshima trip planning tools for AI assistants: a timed day plan for your date, Freepass or single tickets, Enoden fares, trains from Tokyo, cherry blossom, hydrangea and autumn leaves dates, holidays and crowd levels, temple hours and fees, and walking times. Same code and data as the planning tools on [kamakura.info](https://kamakura.info), an independent Kamakura guide.

- **Endpoint:** `https://kamakura.info/mcp` (MCP Streamable HTTP, public, no sign-in, no API key)
- **Docs:** [kamakura.info/ai-assistants](https://kamakura.info/ai-assistants/)
- **MCP Registry:** `info.kamakura/kamakura-trip-planner`
- **npm:** `kamakura-trip-planner-mcp` (stdio bridge to the endpoint, for clients that only run local servers)

## Tools

All tools are read-only (`readOnlyHint: true`), take only trip details and store nothing.

| Tool | What it answers |
|---|---|
| `plan_day` | Timed one- or two-day plan for a date from Tokyo, Shinjuku, Shinagawa or Yokohama: trains, walks, opening-time waits, fares, entry fees, crowd level and bloom season. Renders a route map card in ChatGPT and MCP Apps hosts. |
| `compare_passes` | Enoshima-Kamakura Freepass vs Enoden Noriorikun day pass vs single IC-card tickets, per adult and per group. Renders a ticket receipt card. |
| `enoden_fare` | Fare, minutes and stops between any two of the 15 Enoden stations. |
| `bloom_forecast` | Likely cherry blossom, hydrangea, ginkgo and maple dates, from Japan Meteorological Agency records. Renders a season calendar card. |
| `date_check` | Weekday, Japanese national holiday, crowd level, bloom season and tips for a date. |
| `sight_info` | Hours by month, adult and child fees, extra tickets, visit time and nearest station of temples, shrines and sights. |
| `walk_time` | Walking minutes and distance between any two of 34 places. |
| `getting_there` | Line, changes, minutes and IC fare to Kamakura, Kita-Kamakura or Enoshima from Tokyo, Shinjuku, Shibuya, Shinagawa, Yokohama, Haneda, Narita or Fujisawa. |

The tools answer in English.

## Connect

Remote (recommended):

```json
{
  "mcpServers": {
    "kamakura-trip-planner": {
      "type": "streamable-http",
      "url": "https://kamakura.info/mcp?src=mcp"
    }
  }
}
```

Claude: Settings → Connectors → Add custom connector → `https://kamakura.info/mcp?src=claude`

Claude Code: `claude mcp add --transport http kamakura-trip-planner https://kamakura.info/mcp?src=mcp`

Local stdio bridge (Node.js 18+):

```json
{
  "mcpServers": {
    "kamakura-trip-planner": {
      "command": "npx",
      "args": ["-y", "kamakura-trip-planner-mcp"]
    }
  }
}
```

## Example prompts

1. "Plan a day trip to Kamakura from Tokyo on 12 June 2027."
2. "Is the Enoshima-Kamakura Freepass worth it from Shinjuku for two adults?"
3. "When are the hydrangeas out in Kamakura next year?"
4. "What does the Great Buddha cost and how far is it from Hase Station?"
5. "Will Kamakura be crowded on 3 May?"

## Data and privacy

Fares come from JR East, Odakyu and the Enoshima Electric Railway; bloom dates from Japan Meteorological Agency observations at Yokohama; hours and fees from the temples and sights; walking times from OpenStreetMap routing. Every answer links to the matching page on kamakura.info with its sources.

The server asks for no name, contact or payment details and does not store or log requests. Privacy: [kamakura.info/privacy](https://kamakura.info/privacy/#ai-assistants). Terms: [kamakura.info/terms](https://kamakura.info/terms/).

kamakura.info is an independent guide. It is not a temple, shrine, railway company or tourism office.

## This repository

The hosted server is not open source. This repository holds the stdio bridge published to npm (`index.js`, MIT) and the listing files. Issues and questions: open an issue or write to info@kamakura.info.
