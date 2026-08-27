# Farebox — Product Roadmap 🗺️

> **North star:** Make early-stage travel planning feel like one conversation instead of a sequence of disconnected searches.

Farebox is currently a prototype. The roadmap is deliberately evidence-driven: validate the core interaction before adding expensive integrations and infrastructure.

---

## Current state

### V0 — Concept prototype ✅

**Goal:** Prove the end-to-end interaction.

- [x] Natural-language destination search
- [x] Trip-duration extraction
- [x] Cheapest sample fare ranking
- [x] Low-cost-carrier tagging
- [x] Full fare comparison
- [x] Destination itinerary templates
- [x] Skyscanner comparison link
- [x] Responsive web prototype
- [x] Public GitHub Pages deployment

**Current data model:** Sample/mock flight data and static itinerary templates.

---

# Phase 1 — Validate the problem 🔎

**Objective:** Determine whether the combined flight-discovery + itinerary experience creates meaningful user value.

### User research

- [ ] Test with 10–20 budget travelers
- [ ] Observe users completing a realistic travel-search task
- [ ] Capture where users hesitate or abandon
- [ ] Ask what they would normally use instead
- [ ] Identify whether the itinerary is genuinely useful or just “nice to have”

### Product metrics

Track:

| Metric | Why it matters |
|---|---|
| Search completion rate | Can users express their intent successfully? |
| Search → results time | Does natural language reduce interaction friction? |
| Results → itinerary rate | Is planning a meaningful continuation of flight discovery? |
| External comparison click | Does the user want to continue toward booking? |
| Repeat search rate | Is the experience useful enough to explore alternatives? |
| Qualitative usefulness score | Does the output actually help trip planning? |

### Exit criteria

Move to Phase 2 only if users demonstrate meaningful engagement with the combined journey.

---

# Phase 2 — Add real flight data ✈️

**Objective:** Replace sample fares with trustworthy live search results.

### Discovery

Evaluate suitable providers based on:

- Coverage from India/Chennai
- Pricing and free-tier availability
- API stability
- Rate limits
- Search latency
- Licensing/commercial terms
- Ability to support round trips and flexible dates

### Build

- [ ] Introduce a flight-search API
- [ ] Add date inputs
- [ ] Add return-trip handling
- [ ] Add passenger count
- [ ] Add airport/route normalization
- [ ] Add live price timestamps
- [ ] Add API error states
- [ ] Add loading states
- [ ] Add caching where appropriate

### Product change

Move from:

**“Sample cheapest fare”**

to:

**“Best available fare for your requested trip.”**

---

# Phase 3 — Understand richer travel intent 🧠

**Objective:** Move beyond destination + duration.

Example:

> “Find me a 5-day Vietnam trip from Chennai in November under ₹40,000. I like beaches, nightlife and food.”

Farebox should extract:

```text
Origin        → Chennai
Destination   → Vietnam
Duration      → 5 days
Dates         → November
Budget        → ₹40,000
Interests     → Beaches + nightlife + food
Travel style  → Budget
```

### Planned capabilities

- [ ] Date extraction
- [ ] Budget extraction
- [ ] Origin extraction
- [ ] Interest extraction
- [ ] Travel-style extraction
- [ ] Flexible-date interpretation
- [ ] Multi-destination intent
- [ ] Clarifying questions for missing/ambiguous inputs

### Example clarification

> “I found Vietnam. Do you have a preferred month, or should I search for the cheapest period?”

This changes the product from a parser into an **intent-aware travel assistant**.

---

# Phase 4 — AI-powered itinerary planning 🤖

**Objective:** Replace static templates with personalized itinerary generation.

### Inputs

- Destination
- Trip duration
- Budget
- Interests
- Travel style
- Flight arrival/departure times
- Accommodation area
- Mobility preferences

### Output

```text
Trip overview
↓
Day-by-day itinerary
↓
Estimated daily spend
↓
Travel time between activities
↓
Food recommendations
↓
Budget alternatives
```

### Technical direction

The AI layer should be moved behind a backend/API proxy rather than exposing credentials in the browser.

### Product principle

AI should not simply generate text.

It should make the recommendation **more useful because it understands the user's constraints**.

---

# Phase 5 — Recommendation engine 🎯

**Objective:** Help users choose between flight options rather than simply sort by price.

Instead of:

> Cheapest: ₹13,500

Farebox could explain:

> **Best value — ₹14,200**
>
> ₹700 more than the cheapest option, but with a direct flight and a shorter journey.

### Ranking dimensions

- Price
- Duration
- Stops
- Departure time
- Arrival time
- Airline
- Baggage
- User preferences
- Overall trip cost

This moves Farebox from **price search** toward **decision support**.

---

# Phase 6 — Complete the travel-planning loop 🌍

Longer-term experience:

```text
Tell Farebox where you want to go
              ↓
Understand your constraints
              ↓
Find live flight options
              ↓
Explain the best-value choices
              ↓
Build a personalized itinerary
              ↓
Estimate total trip budget
              ↓
Compare / book externally
              ↓
Save the trip
              ↓
Refine the plan
```

Potential future capabilities:

- [ ] Saved trips
- [ ] Budget tracking
- [ ] Accommodation suggestions
- [ ] Airport transfer suggestions
- [ ] Travel checklist
- [ ] Visa/document reminders
- [ ] Price-change monitoring
- [ ] Collaborative trip planning

---

# Prioritization framework

The roadmap should not be treated as a checklist where every feature must be built.

Each feature should be evaluated using:

**User value × Evidence × Strategic differentiation ÷ Build complexity**

### Highest priority

Features that:

1. Solve a demonstrated user problem
2. Improve the core travel-planning journey
3. Can be validated quickly
4. Create meaningful differentiation

### Lower priority

Features that:

- Add complexity without validated demand
- Recreate commodity OTA functionality
- Require significant infrastructure before the core value is proven

---

# Product risks

| Risk | Mitigation |
|---|---|
| Users prefer traditional flight search | Test natural-language vs. structured search |
| Live API costs become too high | Validate willingness/value before scaling |
| AI itineraries feel generic | Ground recommendations in user constraints |
| Price accuracy creates distrust | Show timestamps and provider/source clearly |
| Too many features dilute the product | Keep the core journey focused |
| Users only want cheap flights | Measure itinerary engagement before expanding AI |

---

# Success definition

Farebox succeeds if users can go from:

> **“I want to take a budget trip somewhere.”**

to:

> **“I know where to go, which flight is best for me, roughly what it will cost, and what I can do when I arrive.”**

with significantly less friction than using separate travel-planning tools.

---

## Current project links

- [🚀 Live prototype](https://balaji-s-here.github.io/Farebox/)
- [📖 Product case study](CASE_STUDY.md)
- [🏠 GitHub repository](https://github.com/balaji-s-here/Farebox)
