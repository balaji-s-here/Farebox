# Case Study: Farebox — Natural-Language Cheap Flight Discovery

**Role:** Product Manager — Solo Build, AI-Assisted  
**Status:** Prototype / Proof of Concept  
**Timeframe:** TBD  
**Platform:** Web — GitHub Pages

---

## 1. The problem

Travel planning is fragmented.

A traveler looking for an affordable trip typically has to move between multiple tools: one for finding flights, another for comparing airlines and fares, and several more for researching what to do after arriving.

This creates unnecessary context switching and makes a simple question surprisingly difficult to answer:

> **“What is the cheapest way for me to get there, and what can I do once I arrive?”**

Farebox was created to explore whether this journey could be simplified into a single interaction.

Instead of requiring structured flight-search fields, the user can type a request in plain English, such as:

> *“Find cheap flights to Thailand for 5 days.”*

The prototype interprets the destination and trip duration, surfaces the three cheapest options, provides a broader fare comparison with low-cost carriers clearly identified, and generates a budget-oriented day-by-day itinerary from the available destination templates.

The goal was not to build another flight aggregator. The goal was to validate whether **intent-first travel discovery** could provide a better starting point for budget travelers.

---

## 2. Product hypothesis

**If travelers can describe their trip naturally instead of filling out multiple search fields, and immediately receive both affordable flight options and a starting itinerary, then the initial travel-planning experience can become faster and more useful.**

The prototype therefore focused on validating three core behaviors:

1. Can users express a travel requirement naturally?
2. Can that intent be converted into useful flight options?
3. Can flight discovery be connected directly to trip planning?

---

## 3. User stories & acceptance criteria

| User story | Acceptance criteria | Prototype status |
|---|---|---|
| As a traveler, I want to search for flights using normal language | The system identifies a supported destination and trip duration from free text | ✅ Done — lightweight parsing across supported destinations |
| As a budget traveler, I want to quickly identify the cheapest option | Results are sorted by price and the cheapest option is surfaced prominently | ✅ Done |
| As a traveler, I want to know which options are low-cost carriers | LCCs are visibly tagged in the results | ✅ Done |
| As a traveler, I want to compare more than the cheapest option | A full list of available sample airline options is displayed | ✅ Done |
| As a traveler, I want an initial plan for my trip | A day-by-day itinerary is assembled according to the requested trip length | ✅ Done — destination-specific itinerary templates |
| As a traveler, I want to continue researching or booking | A comparison link takes the user to Skyscanner | ✅ Done — public comparison/deep link |
| As a user, I want immediate feedback while entering my search | Destination, trip duration and origin are reflected in the search preview | ✅ Done |
| As a user, I want the experience to work without installation | The prototype runs as a single static web page | ✅ Done |

---

## 4. MVP scope

I deliberately kept the first version narrow.

### Included in the MVP

- Natural-language flight search
- Chennai (MAA) as the origin
- Supported destination routes
- Trip-duration extraction
- Cheapest-flight ranking
- Low-cost-carrier identification
- Full fare comparison
- Destination-specific itinerary templates
- Budget-oriented itinerary recommendations
- Skyscanner comparison link
- Responsive web interface

### Explicitly excluded from the MVP

- Live flight inventory
- Real-time pricing
- Flight booking
- User accounts
- Payment
- Dynamic AI itinerary generation
- Backend infrastructure
- Personalization based on user history

This allowed the prototype to answer the product question without turning the project into a full travel-tech build.

---

## 5. Key product decisions & trade-offs

### 5.1 Natural-language search vs. traditional search form

Traditional flight products generally begin with structured inputs: origin, destination, departure date, return date and passenger count.

For this experiment, I intentionally removed most of that complexity.

The user starts with an intent such as:

> *“Find cheap flights to Vietnam for 6 days.”*

The prototype extracts the destination and duration using lightweight parsing.

**Why:** The objective was to test the interaction model, not build a production-grade NLP system.

**Trade-off:** The current parser only understands a predefined set of destinations and simple duration expressions.

**PM lesson:** Start with the narrowest implementation that can validate the desired user behavior before introducing unnecessary technical complexity.

---

### 5.2 Live flight APIs vs. realistic mock data

Real-time flight data would make the prototype more powerful, but integrating a production-quality flight data provider introduces API keys, provider limitations, rate limits, backend requirements and additional development effort.

Rather than make the live API integration a prerequisite for validating the concept, I used a deterministic sample fare dataset.

The prototype therefore focuses on the **experience and decision flow**, while clearly communicating that the displayed fares are sample/template data.

**Trade-off:** Users cannot rely on the displayed prices for actual booking decisions.

**PM lesson:** Separate the product hypothesis from infrastructure dependencies. If the hypothesis can be tested without a live data source, don't let infrastructure become the blocker to learning.

---

### 5.3 Static itinerary templates vs. live AI generation

The itinerary component is intentionally template-based in the current prototype.

Each supported destination has a small library of budget-oriented day plans. The application assembles those templates according to the requested trip duration.

**Why:** This keeps the prototype completely static, inexpensive to host and easy to demonstrate without exposing an API key or requiring a backend.

**Trade-off:** The itinerary is not personalized or dynamically generated by AI.

**Future direction:** Replace the template library with a backend-proxied AI itinerary service once the core product interaction has been validated.

**PM lesson:** Use AI where it creates meaningful product differentiation, but don't introduce an AI dependency before the underlying user journey has been proven.

---

### 5.4 Website vs. native mobile application

I chose a web prototype rather than a native mobile application.

The objective at this stage was learning, not distribution at scale. A single HTML/CSS/JavaScript application could be built, tested and shared without app-store submission, native development or infrastructure costs.

GitHub Pages also provides a free hosting path for a static prototype.

**Trade-off:** The prototype does not provide the full capabilities of a production mobile travel application.

**PM lesson:** The right MVP platform is the one that minimizes the cost of learning, not necessarily the platform that the eventual product will use.

---

### 5.5 Comparison experience vs. booking experience

Farebox does not attempt to become an OTA or booking platform in the MVP.

Instead, once the user has discovered the cheapest options, the prototype provides a route to continue comparison through Skyscanner.

This creates a clear product boundary:

**Discover → Compare → Continue externally**

rather than:

**Discover → Build booking infrastructure**

**PM lesson:** Own the part of the journey where the product provides differentiated value, while using established platforms for downstream actions that do not need to be reinvented during MVP validation.

---

## 6. Prototype architecture

The prototype intentionally uses a very lightweight architecture:

**Frontend**
- Single HTML file
- Embedded CSS
- Vanilla JavaScript
- Responsive interface

**Data**
- Mock flight dataset
- Deterministic airline pricing logic
- Destination-specific itinerary templates

**Hosting**
- GitHub Pages
- No server required
- No build pipeline required

The result is a zero-backend prototype that can be opened directly in a browser and shared through a public URL.

---

## 7. What the prototype demonstrates

The most important output of the project is not the individual flight cards or the visual design.

It demonstrates an end-to-end product concept:

**Natural-language intent**

↓

**Destination + trip-duration understanding**

↓

**Cheapest options**

↓

**Low-cost-carrier identification**

↓

**Full fare comparison**

↓

**Trip itinerary**

↓

**External flight comparison**

This creates a more complete travel-planning journey than simply returning a flight price.

---

## 8. What I learned

### 1. Narrow natural-language interfaces can be prototyped without heavy NLP

For a constrained problem, lightweight parsing can demonstrate the interaction before investing in a sophisticated language-processing stack.

### 2. Flight comparison is not the strongest differentiation

Showing cheap flights is valuable, but it is also highly commoditized.

The more interesting product opportunity is connecting **flight discovery with what happens after the flight is booked**.

That is where Farebox begins moving from a flight-search utility toward a travel-planning assistant.

### 3. Constraints can improve MVP decisions

Instead of treating the lack of live APIs, backend infrastructure and budget as blockers, I used them to define the MVP boundary.

### 4. A prototype should answer a product question

The objective was not to prove that I could build a complete flight-booking platform.

It was to test:

> **Can a traveler describe their trip naturally and get enough useful information in one place to move from “I want to go somewhere” to “I know roughly how I can get there and what I can do”?**

The prototype provides a tangible way to test that hypothesis.

---

## 9. Current limitations

### Data limitations

- Flight prices are sample data, not live fares.
- Airline availability is not real-time.
- Chennai is the fixed origin.
- Destination coverage is limited to the routes currently supported by the prototype.

### Product limitations

- Natural-language understanding is limited to supported destinations and simple duration expressions.
- Itineraries are predefined templates rather than dynamically generated plans.
- There is no user personalization.
- There are no accounts, saved trips or booking capabilities.

### Technical limitations

- No backend
- No live flight API
- No database
- No automated testing
- No analytics
- No caching
- No production authentication or security layer

These limitations are intentional MVP trade-offs rather than hidden gaps.

---

## 10. What's next

The next version would move Farebox from a demonstration prototype toward a testable product.

### Phase 1 — Validate the experience

- Put the prototype in front of real travelers.
- Capture search behavior and feedback.
- Identify which part of the experience creates the most value.
- Measure whether users continue from flight discovery to itinerary planning.

### Phase 2 — Introduce live data

- Integrate a suitable flight-data provider.
- Replace sample fares with real availability and pricing.
- Expand origin and destination coverage.
- Add dates and more flexible trip parameters.

### Phase 3 — Introduce dynamic AI planning

- Replace static itinerary templates with AI-generated itineraries.
- Add budget, interests and travel style as inputs.
- Generate plans based on actual trip duration and destination.
- Move AI/API calls behind a secure backend.

### Phase 4 — Build the product loop

**“Tell Farebox where you want to go.”**

→ Find the best-value flights  
→ Explain why the options differ  
→ Build a personalized itinerary  
→ Estimate the trip budget  
→ Compare/book through relevant providers  
→ Save and refine the trip

---

## 11. Product takeaway

Farebox started as a simple question:

> **Can flight discovery and trip planning be brought together through natural language?**

The prototype shows that the concept can be expressed in a lightweight, low-cost product without requiring a full travel-booking infrastructure.

The next product question is no longer **“Can I build this?”**

It is:

> **“Do travelers find enough value in this combined experience to use it instead of switching between multiple travel-planning tools?”**

That is the hypothesis the next iteration should test.

---

## 🔗 Project links

- [Live prototype](https://balaji-s-here.github.io/Farebox/)
- [GitHub repository](https://github.com/balaji-s-here/Farebox)
- [Roadmap](ROADMAP.md)
