<h1 align="center">Israa Essa</h1>

<p align="center">
  <strong>Flutter Developer</strong> · Offline-First Business Apps · Arabic RTL<br>
  <sub>Libya</sub>
</p>

<p align="center">
  <a href="https://www.linkedin.com/in/israa-essa-3b5644384">
    <img src="https://img.shields.io/badge/LinkedIn-1B4DB1?style=flat-square&logo=linkedin&logoColor=white" alt="LinkedIn" />
  </a>
  <a href="https://github.com/Israa050?tab=repositories">
    <img src="https://img.shields.io/badge/Projects-23305C?style=flat-square&logo=github&logoColor=white" alt="Projects" />
  </a>
  <a href="https://t.me/ISRA_ESSA">
    <img src="https://img.shields.io/badge/Telegram-26A5E4?style=flat-square&logo=telegram&logoColor=white" alt="Telegram" />
  </a>
  <a href="mailto:YOUR_EMAIL_HERE">
    <img src="https://img.shields.io/badge/Email-23305C?style=flat-square&logo=gmail&logoColor=white" alt="Email" />
  </a>
</p>

<p align="center">
  <img src="assets/money-log-transactions.jpg" alt="Money Log — transaction list with live balance summary" width="215" />
  &nbsp;
  <img src="assets/money-log-add.jpg" alt="Money Log — add transaction sheet" width="215" />
  &nbsp;
  <img src="assets/money-log-empty.jpg" alt="Money Log — empty state" width="215" />
</p>

<p align="center">
  <sub><em>Money Log — a fully reactive Flutter ledger. Every screen driven by a live SQLite stream.</em></sub>
</p>

---

I build Flutter applications that keep working when the network doesn't.

Most mobile apps assume a stable connection. In the markets I build for, that assumption breaks daily — so my work centres on local-first architecture: the app runs entirely on-device, holds a single source of truth in SQLite, and syncs cleanly when connectivity returns. Alongside that, I care about the parts that survive a codebase's second year — typed schemas, tested state machines, and CI that refuses to merge a regression.

I work in both **Arabic and English**, and give real attention to RTL correctness rather than treating it as a translation pass.

---

## Featured Work

| Project | What it demonstrates | Stack |
| :--- | :--- | :--- |
| **[Money Log](https://github.com/Israa050/money-log)** | Fully reactive architecture — every screen driven by a live database stream, no manual refresh anywhere. Optimistic delete with a countdown undo. | Bloc · Drift · get_it · CI |
| **[Sabil](https://github.com/Israa050/Sabil)** | Fintech MVP: phone/OTP auth, AI-assisted KYC face verification, real-time credit scoring, Arabic RTL-first UI. | Cubit · Dio · go_router |
| **[Pets Finder](https://github.com/Israa050/Pets-Finder)** | Clean Architecture end to end, with unit, widget, and integration test coverage. | Cubit · Dio · Clean Arch |
| **[Flutter Core Utils](https://github.com/Israa050/Flutter-Core-Utils)** | Reusable core module consumed as a git submodule — shared configs and architecture to bootstrap projects consistently. | Dart · Architecture |
| **[Quotes App](https://github.com/Israa050/Quotes-App)** | Native interop via platform channels — a Kotlin shake detector on the Android side wired through to Flutter. | Flutter · Kotlin · Platform Channels |
| **[Movies DB](https://github.com/Israa050/Movies-DB)** | Infinite-scroll pagination, Hive offline caching, Sentry error tracking, light/dark theming. | Cubit · Hive · Sentry |

---


## Engineering Decisions I've Made

The choices below are documented in the repositories themselves — I write down the reasoning, including the trade-offs, not just the outcome.

- **Money as integer minor units, never `double`** *(Money Log)* — IEEE 754 can't represent most decimal fractions exactly, so summed amounts drift over time. Whole minor units keep every operation exact; conversion to a display string happens only at the UI boundary.
- **Balance derived from queries, never stored** *(Money Log)* — one source of truth means no reconciliation step, and no way for a cached total to disagree with the ledger.
- **Tests run against a real in-memory database, not mocks** *(Money Log)* — mocking the data layer tests the mock, not the schema. A real SQLite instance per test catches constraint violations, defaults, and enum round-tripping that mocks silently pass.
- **Shared core extracted as a git submodule, not copy-pasted** *(Flutter Core Utils)* — duplicated base configs diverge the moment one project fixes a bug. A consumed module means the fix propagates instead of rotting in three places.
- **Offline cache with explicit error reporting** *(Movies DB)* — Hive caches pages so the list survives a dropped connection, and Sentry captures what actually failed in production rather than leaving silent empty states.
- **RTL designed in from the start, not retrofitted** *(Sabil)* — direction-aware layout, numerals, and input behaviour are architectural, not a translation pass. Retrofitting them means revisiting every screen.
- **Drop to native only where the platform requires it** *(Quotes App)* — sensor access lives in Kotlin behind a platform channel; everything above it stays in Dart, so the native surface is small and testable.

---

## Toolbox

| | |
| :--- | :--- |
| **Language & Framework** | Dart · Flutter · Kotlin |
| **State Management** | Bloc / Cubit · Freezed |
| **Data & Backend** | Drift (SQLite) · Hive · Supabase · Firebase · REST via Dio + Retrofit |
| **Architecture** | Clean Architecture · SOLID · Design Patterns · Dependency Injection (get_it) |
| **Testing & Quality** | `flutter_test` · `bloc_test` · `mocktail` · widget & integration tests · Sentry |
| **Delivery** | GitHub Actions CI · signed release builds & Google Play publishing · Git submodules |
| **Design** | Figma to Flutter · design tokens · light/dark theming · responsive layouts · RTL |

---

## Currently

Extending **Money Log** into a full offline-first ledger — relational categories and accounts via real Drift migrations, with `bloc_test` and `mocktail` coverage across the write paths.

Writing about Flutter architecture in Arabic on [LinkedIn](LINKEDIN_URL_HERE) — reactive streams, state modelling, and the decisions behind them.

---

<p align="center">
  <sub>Open to remote roles, freelance projects, and collaboration.</sub>
</p>
