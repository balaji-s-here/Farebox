# Farebox — Ready to Fly ✈️

**A natural-language cheap-flights search prototype with AI-generated itineraries.**

Type something like *"find cheap flights to Thailand for 5 days"* and get back the 3 cheapest options, a full fare comparison flagging low-cost carriers, and a live AI-generated day-by-day itinerary.


---

## What this is

A **product prototype**, built to validate a real user problem before investing in a full build: travel planning takes too long and involves too many disconnected tools (fare search, LCC comparison, itinerary research). This is a single-page proof of concept, not production software — see [Known Limitations](#known-limitations--technical-debt) below.

## Features

- **Natural-language search** — parses destination + trip length from a plain-English query
- **Top-3 cheapest fares** — ranked, with low-cost-carrier tagging
- **Full fare comparison list** — all airlines for the route, sorted by price
- **Day-by-day itinerary** — budget-first, walkable, pre-written per destination and assembled to match trip length
- **Skyscanner compare link** — deep-links out to Skyscanner's public search (no partner API required)

## Tech stack

| Layer | Choice | Why |
|---|---|---|
| Frontend | Single-file HTML/CSS/JS | Zero build tooling, zero hosting cost, fastest path to a testable prototype |
| Flight data | **Mock/sample dataset** (11 routes ex-Chennai) | No flight API key wired in yet — see roadmap |
| Itinerary | **Static template library** (per destination) | Chosen deliberately to keep hosting 100% free — a live AI call needs a backend proxy to protect an API key, which this static-site setup doesn't have. See roadmap for the live-AI path. |
| Hosting | GitHub Pages | Free, no server, deploys from a static `index.html` |

## What's mock vs. live

- 🟡 **Mock:** all flight prices, airlines, durations — sample data, not real fares
- 🟡 **Static:** itineraries — pre-written per destination, assembled to match the requested trip length. Not dynamically generated on this hosting setup; see `ROADMAP.md` Phase 1 for the live-AI version (requires a backend proxy + API key)

## Known limitations / technical debt

This was built fast, as a prototype, not for production efficiency. Before this becomes a real product, it needs:

- **No live flight data** — prices are hardcoded sample data, not connected to Amadeus/Kiwi/any real source yet
- **No backend / no API key security** — the Claude API call happens directly from the browser; a real version needs a backend proxy so keys aren't exposed client-side
- **No caching** — every search recomputes from scratch; a real version should cache flight prices and itinerary responses
- **No build pipeline** — everything is one unminified HTML file; no bundling, code-splitting, or asset optimization
- **No error handling for edge cases** — unrecognized destinations, API failures, and rate limits are only minimally handled
- **No automated tests** — zero test coverage; all validation so far is manual
- **No analytics** — no way to see what people actually search for yet
- **Limited destination coverage** — only 11 hardcoded routes from Chennai

See `ROADMAP.md` for how these get addressed, and `CASE_STUDY.md` for the product thinking behind the build.

## Running locally

No installation needed — it's a static file:
1. Download `index.html`
2. Double-click to open in any browser, or run a local server (`python3 -m http.server`) and visit `localhost:8000`

## License

Prototype for personal portfolio / learning-in-public use.
