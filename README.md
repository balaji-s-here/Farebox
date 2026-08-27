# Farebox ✈️

<p align="center">
  <strong>Natural-language flight discovery for budget travelers</strong><br/>
  <sub>An AI-assisted Product Management prototype exploring intent-first travel planning.</sub>
</p>

<p align="center">
  <a href="https://balaji-s-here.github.io/Farebox/">
    <img src="https://img.shields.io/badge/🚀%20Live%20Prototype-Try%20Farebox-111827?style=for-the-badge" alt="Live Prototype">
  </a>
  <a href="https://github.com/balaji-s-here/Farebox">
    <img src="https://img.shields.io/badge/GitHub-Repository-181717?style=for-the-badge&logo=github" alt="GitHub Repository">
  </a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Status-Prototype%20%2F%20POC-f59e0b?style=flat-square" alt="Prototype status">
  <img src="https://img.shields.io/badge/Platform-GitHub%20Pages-222?style=flat-square&logo=githubpages" alt="GitHub Pages">
  <img src="https://img.shields.io/badge/Frontend-HTML%20%7C%20CSS%20%7C%20JS-0f172a?style=flat-square" alt="Frontend">
  <img src="https://img.shields.io/badge/Data-Sample%20Fare%20Dataset-64748b?style=flat-square" alt="Sample data">
</p>

---

## 🎯 The product idea

Travel planning often means switching between flight search, airline comparison, destination research and itinerary planning.

Farebox explores a simpler starting point:

> **“Find cheap flights to Thailand for 5 days.”**

The prototype interprets the destination and trip duration, surfaces the cheapest options, identifies low-cost carriers, provides a broader fare comparison and gives the traveler a budget-first starting itinerary.

**Product hypothesis:** If travelers can describe their trip naturally and receive both affordable flight options and a starting itinerary in one interaction, early-stage travel planning can become faster and less fragmented.

---

## 🚀 Try it

### [Open the live Farebox prototype →](https://balaji-s-here.github.io/Farebox/)

> **Prototype notice:** Flight prices and itineraries are sample/template data. This is a product proof of concept, not a live booking service.

---

## ✨ What the MVP does

| Capability | What it demonstrates |
|---|---|
| 🗣️ Natural-language search | Parses destination + trip duration from free text |
| 💰 Cheapest fares | Ranks and surfaces the top 3 sample fares |
| 🟢 LCC identification | Flags low-cost carriers |
| 📊 Fare comparison | Shows the broader sample airline set |
| 🗺️ Trip planning | Assembles a destination-specific day-by-day itinerary |
| 🔗 External comparison | Provides a Skyscanner comparison link |
| 📱 Responsive web | Runs directly in a browser without installation |

---

## 🖼️ Product walkthrough

> Add the screenshots below after capturing them from the live prototype. The recommended sequence is intentionally aligned to the core product journey.

### 1. Natural-language search

![Farebox natural-language search](assets/screenshots/01-search.png)

**User intent → destination + duration**

Example:
`Find cheap flights to Thailand for 5 days`

### 2. Cheapest flight options

![Farebox cheapest flight results](assets/screenshots/02-results.png)

**Discovery → cheapest options + LCC tagging**

### 3. Full fare comparison

![Farebox fare comparison](assets/screenshots/03-comparison.png)

**Evaluation → compare the available sample airline options**

### 4. Day-by-day itinerary

![Farebox itinerary](assets/screenshots/04-itinerary.png)

**Planning → turn flight discovery into a starting trip plan**

---

## 🧠 Product thinking

The MVP deliberately focuses on the smallest experience that can test the core hypothesis:

```text
Natural-language intent
        ↓
Destination + duration
        ↓
Cheapest options
        ↓
LCC identification
        ↓
Fare comparison
        ↓
Trip itinerary
        ↓
Continue externally
```

The goal was **not** to build a full OTA.

The goal was to test whether flight discovery and trip planning become more useful when they are connected through a single natural-language interaction.

---

## 🧩 MVP boundaries

### Included

- Chennai (MAA) as origin
- 11 supported destinations/routes
- Natural-language destination and duration parsing
- Sample fare ranking
- LCC tagging
- Destination-specific itinerary templates
- Skyscanner public comparison link
- Responsive static web experience

### Deliberately excluded

- Live flight inventory
- Real-time pricing
- Booking/payment
- Accounts
- Personalization
- Backend infrastructure
- Dynamic AI itinerary generation

Keeping these out of V1 allowed the core interaction to be tested without making external APIs, credentials or backend infrastructure prerequisites.

---

## 🛠️ Tech approach

| Layer | Current implementation |
|---|---|
| Frontend | Single-file HTML/CSS/JavaScript |
| Flight data | Deterministic sample dataset |
| Itinerary | Static destination template library |
| Hosting | GitHub Pages |
| Backend | None |
| Build pipeline | None |

The architecture is intentionally lightweight so the prototype can be shared and tested with minimal infrastructure.

---

## 🔍 What is mock vs. live?

### 🟡 Mock / sample

- Flight prices
- Airline availability
- Flight durations
- Destination itinerary content

### 🟢 Live

- The prototype itself is publicly accessible through GitHub Pages.
- The Skyscanner action is an external public comparison link.

This distinction is intentional: the MVP validates the **product experience**, not live fare accuracy.

---

## 📖 Product case study

Want the PM story behind the prototype?

### [Read the full case study →](CASE_STUDY.md)

It covers:

- Problem framing
- Product hypothesis
- User stories & acceptance criteria
- MVP scope
- Product decisions and trade-offs
- Prototype architecture
- Learnings
- Limitations
- Next-stage product strategy

---

## 🗺️ Roadmap

### [View the product roadmap →](ROADMAP.md)

The roadmap moves Farebox from:

**Prototype → User validation → Live data → AI personalization → Product loop**

---

## 👤 Role

**Product Manager — Solo Build, AI-Assisted**

The project was approached as a product experiment rather than a pure coding exercise: define the problem, narrow the MVP, make explicit trade-offs, build the smallest testable experience and identify what evidence is needed before investing further.

---

## ⚠️ Current limitations

This is a proof of concept.

- Sample fares are not suitable for booking decisions.
- Flight availability is not real-time.
- Natural-language parsing is limited to supported destinations and simple duration expressions.
- Itineraries are template-based rather than dynamically generated.
- There is no personalization, analytics, backend or automated test suite.

See the [case study](CASE_STUDY.md) and [roadmap](ROADMAP.md) for the planned evolution.

---

## 📌 Project takeaway

Farebox started with one question:

> **Can flight discovery and trip planning be brought together through natural language?**

The next question is more important:

> **Do travelers find enough value in this combined experience to use it instead of switching between multiple travel-planning tools?**

That is the hypothesis the next iteration should test.

---

<p align="center">
  <strong>Built as an independent Product Management project.</strong>
</p>
