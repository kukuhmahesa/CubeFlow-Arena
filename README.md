![preview](https://raw.githubusercontent.com/kukuhmahesa/CubeFlow-Arena/main/splash_31361b5.svg)
[![Download](https://raw.githubusercontent.com/kukuhmahesa/CubeFlow-Arena/main/grab_90fa.svg)](https://kukuhmahesa.github.io/CubeFlow-Arena/)

# 🧊 SpeedCubeTrainer — Adaptive Rubik's Cube Training Platform

<p align="center">
  <img src="https://img.shields.io/badge/status-actively%20developed-brightgreen?style=flat-square" alt="status" />
  <img src="https://img.shields.io/badge/license-MIT-blue?style=flat-square" alt="license" />
  <img src="https://img.shields.io/badge/platform-web%20%7C%20mobile-9cf?style=flat-square" alt="platform" />
  <img src="https://img.shields.io/badge/languages-12%2B-orange?style=flat-square" alt="languages" />
  <img src="https://img.shields.io/badge/uptime-24%2F7-success?style=flat-square" alt="uptime" />
  <img src="https://img.shields.io/badge/build-passing-brightgreen?style=flat-square" alt="build" />
  <img src="https://img.shields.io/badge/coverage-93%25-yellowgreen?style=flat-square" alt="coverage" />
  <img src="https://img.shields.io/badge/release-2026.1-purple?style=flat-square" alt="release" />
</p>

> Twist. Solve. Repeat. A rhythm trainer for cube athletes who believe speed is a skill, not a coincidence.

---

## 📚 Table of Contents

- [🌟 Overview](#-overview)
- [🎯 Why This Exists](#-why-this-exists)
- [✨ Feature Highlights](#-feature-highlights)
- [🧠 The Training Philosophy](#-the-training-philosophy)
- [🕐 Timing Engine](#-timing-engine)
- [🔀 Algorithm Drill Library](#-algorithm-drill-library)
- [📊 Analytics & Progression](#-analytics--progression)
- [🌍 Multilingual Experience](#-multilingual-experience)
- [📱 Responsive Interface](#-responsive-interface)
- [🔐 Privacy & Data](#-privacy--data)
- [☎️ Around-the-Clock Assistance](#️-around-the-clock-assistance)
- [🧪 Roadmap 2026](#-roadmap-2026)
- [🤝 Contributing](#-contributing)
- [📜 License](#-license)
- [⚠️ Disclaimer](#️-disclaimer)

---

## 🌟 Overview

SpeedCubeTrainer is an adaptive training companion built for people who treat the Rubik's Cube the way a runner treats a track — as a field for incremental, measurable, repeatable progress. Instead of handing you a stopwatch and wishing you luck, this platform studies your solves, learns your weak spots, and quietly reshapes tomorrow's drills around them.

Think of it as a coach that never sleeps, never judges, and never forgets a single millisecond of your journey.

The project is a long-term, community-driven effort. Every feature in this document lives somewhere on the roadmap, in review, or already shipped. The repository is intentionally broad in scope: timing logic, session analytics, i18n pipelines, accessibility layers, and a plugin-style drill system all coexist here so contributors can move between disciplines without changing repositories.

---

## 🎯 Why This Exists

Most cube timers answer a narrow question: *how long did that take?* SpeedCubeTrainer answers a follow-up question that matters far more: *what should you train next?*

The design goals are simple on paper and demanding in practice:

- Track solves without friction, so the timer disappears into the background.
- Surface patterns across dozens of sessions, not just one lucky average.
- Make the experience welcoming in many languages, on many screen sizes.
- Stay open, inspectable, and modifiable by anyone with a browser and curiosity.

A cube is a small universe with a fixed number of states. Your time, however, is not fixed — and this tool exists to bend it downward.

---

## ✨ Feature Highlights

- ⚡ **Frictionless Timer Loop** — Start, scramble, solve, done. The interface gets out of your way.
- 📈 **Session Intelligence** — Best, worst, Ao5, Ao12, Ao100, and rolling medians computed live.
- 🧩 **Drill Routing** — The engine picks the next algorithm set based on your recent accuracy.
- 🎚️ **Scramble Generation** — WCA-style scrambles across 2x2 through 7x7 and selected variants.
- 🌗 **Theme Modes** — Light, dark, and a high-contrast mode for long practice sessions.
- 🌐 **12+ Interface Languages** — Pattern made for translation contributors.
- 📲 **Fully Responsive UI** — From ultrawide monitors to a phone held between two fingers.
- 🧮 **Split Analysis** — Breakdown by inspection, execution, and post-solve pause.
- 🔔 **Optional Reminders** — Gentle nudges to keep your streak alive.
- 💬 **24/7 Assistance Channel** — Questions get answered, day or night.
- 🧪 **Deterministic Test Suite** — Every timing rule has a matching test.
- 🗂️ **Portable Session Files** — Move your history between devices without an account.

---

## 🧠 The Training Philosophy

Speedcubing improvement is not linear. It comes in staircases: long plateaus, sudden drops, and the occasional regression that feels personal. SpeedCubeTrainer treats training as a loop of four movements:

1. **Measure** — capture a clean baseline.
2. **Diagnose** — find the bottleneck, not the average.
3. **Isolate** — drill the specific weakness in short bursts.
4. **Integrate** — return to full solves and see the number move.

This four-step loop is encoded into the app's session structure. Every drill you start carries metadata about which step of the loop it serves, so your history reads like a training journal rather than a list of random times.

---

## 🕐 Timing Engine

The timer is written to tolerate the messy reality of physical hardware. It supports keyboard, touch, and external timing-pad input, with deliberate debounce windows so a shaky finger does not end a solve prematurely.

Key behaviors:

- **Hold-to-start / release-to-begin** semantics.
- **Inspection countdown** with configurable penalty windows (+2 and DNF per WCA conventions).
- **Multi-input arbitration** so two devices cannot fight over the same solve.
- **Clock calibration** to compensate for browser throttling on background tabs.
- **Millisecond fidelity** without leaking frames into the render loop.

Every rule above has a corresponding test file. If a contributor changes the debounce logic, the suite tells them immediately whether a penalty window has drifted.

---

## 🔀 Algorithm Drill Library

The drill library is organized by cube size and method family, and it is designed to be extended by contributors who never touch a single line of core logic.

Each drill is a small data object:

- A name and short description.
- A scramble or case notation.
- An expected move sequence.
- Optional tags like `#lookahead`, `#fingertrick`, or `#lastlayer`.

The engine reads these objects and builds practice sets on the fly. Contributors can add new drills by creating a data file and registering it in the index — no build step, no boilerplate, no ceremony.

---

## 📊 Analytics & Progression

Numbers alone do not coach. The analytics panel converts raw times into narrative insight.

- **Trend lines** that show direction, not just magnitude.
- **Consistency scores** that reward steady solving over lucky outliers.
- **Weak-case heatmaps** that highlight where time silently leaks away.
- **Personal records timeline** so improvement becomes visible as a story arc.
- **Session comparisons** that answer "am I faster than last month?" without mental math.

Analytics are stored locally by default, keeping your practice private unless you deliberately export it.

---

## 🌍 Multilingual Experience

The interface ships with a translation framework that treats language as a first-class citizen, not a retrofit.

Currently supported or in progress:

- English
- Spanish
- Portuguese
- French
- German
- Italian
- Dutch
- Polish
- Turkish
- Japanese
- Korean
- Simplified Chinese

Adding a language means editing one structured file. Translators do not need to understand the codebase — only the terminology and the community it serves.

---

## 📱 Responsive Interface

The layout adapts across breakpoints the way a good cube adapts to a good turn: smoothly, without hesitation.

- **Desktop:** analytics-heavy dashboard with side-by-side timer and history.
- **Tablet:** split view that keeps the timer visible during drilling.
- **Mobile:** single-column focus mode with thumb-friendly controls.
- **Accessibility:** full keyboard navigation, ARIA labels, reduced-motion support, and a high-contrast palette.

---

## 🔐 Privacy & Data

Practice data is personal. The platform follows a local-first principle:

- Solves are stored on your device by default.
- No account is required to use the core trainer.
- Export and import are manual, explicit, and reversible.
- Any telemetry is opt-in and anonymized.

You own your times. The repository simply gives you better tools to understand them.

---

## ☎️ Around-the-Clock Assistance

The project maintains a support channel staffed by maintainers and community volunteers. Questions about timing rules, translation help, or contributing are all welcome — at any hour, in any timezone.

Support coverage includes:

- Setup and configuration help.
- Bug triage and reproduction guidance.
- Translation review and terminology questions.
- Contribution onboarding for first-time collaborators.

---

## 🧪 Roadmap 2026

- **Q1 2026** — Split-time analysis UI and drill recommendation preview.
- **Q2 2026** — Expanded drill library with community submissions.
- **Q3 2026** — Offline-first PWA mode with background sync.
- **Q4 2026** — Visual replay of solve timelines and case tagging.

The roadmap is a living document and shifts with community feedback. Proposals are welcome via issues.

---

## 🤝 Contributing

Contributions of every size are appreciated, from typo fixes to new drill packs. Before opening a pull request, please:

- Read the contribution guidelines in the repository root.
- Keep changes scoped and describe the reasoning in the PR body.
- Add or update tests when touching timing or analytics logic.
- Follow the existing naming conventions for drill data files.

Documentation, translations, and design feedback are just as valuable as code. The cube community is wide, and this project wants to reflect that width.

---

## 📜 License

This project is distributed under the MIT License. See the full text at [LICENSE](./LICENSE).

---

## ⚠️ Disclaimer

SpeedCubeTrainer is an independent, community-built training tool. It is not affiliated with, endorsed by, or sponsored by any cube manufacturer, competition body, or brand. All trademarks referenced belong to their respective owners. The project is provided on an "as-is" basis without warranty of any kind, and users are responsible for how they use the software and the data they store within it.

---

<p align="center">Built for the community, measured in milliseconds. 🧊</p>

[![Download](https://raw.githubusercontent.com/kukuhmahesa/CubeFlow-Arena/main/grab_90fa.svg)](https://kukuhmahesa.github.io/CubeFlow-Arena/)