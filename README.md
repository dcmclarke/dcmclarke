# Daniel Clarke

Software developer based in Wicklow, Ireland. I build systems on real operational
data such as turbine telemetry and satellite orbital data.

HDip in Science in Computing (Software), First Class Honours, NCI 2025.
Previously BSc Applied Psychology.

---

## Tech Stack

**Languages:** Python · Java · TypeScript · JavaScript · SQL
**Backend:** FastAPI · Spring Boot · Spring Data JPA · REST APIs · SQLAlchemy · Pydantic
**Frontend:** React · TypeScript · Vite
**Data:** PostgreSQL · MySQL · pandas · NumPy
**Tools:** Git · GitHub Actions · Docker · Docker Compose · Maven · JUnit · Postman

---

## Projects

### [Wind Turbine Icing Detection](https://github.com/dcmclarke/wind-turbine-twin)

Detects ice accretion on turbine blades from real SCADA telemetry, implementing
the IEA Wind Task 19 power-ratio method against data from ETH Zurich's Aventa
AV-7 research turbine.

The first version reported F1 0.86. Then I tested it against a one-line rule —
alarm if power output is zero — and the rule scored slightly higher. My evaluation
set had made perfect recall automatic, so the headline number was measuring the
dataset, not the detector. I rebuilt the evaluation with held-out days and that
rule as the baseline. The detector alarms about an hour later by design, but
raises false alarms on 1 of 11 clean days against the rule's 6. Both versions are
in the repo, including the one that was wrong.

Power curve fitted from 873,000+ readings of normal operation. Architecture
decisions and rejected alternatives are recorded in an ADR log. CI runs the test
suite on every push and fails the build if evaluation metrics drift from a stored
baseline.

**Stack:** Python · FastAPI · PostgreSQL · React/TypeScript · Docker · GitHub Actions
**Live:** [wind-turbine-icing.netlify.app](https://wind-turbine-icing.netlify.app)

---

### [Satellite Proximity Screening](https://github.com/dcmclarke/satellite-collision-detection-tool)

Java 21 / Spring Boot 3 REST API that ingests orbital data for 500+ satellites
from the US Space Force's Space-Track.org API and runs pairwise screening across
~125,000 satellite pairs per run, with tiered risk classification and a React
dashboard.

Built as a final college project and kept honest about its scope: it uses a
simplified distance model rather than SGP4 orbital propagation, so it illustrates
the screening workflow rather than performing real conjunction assessment.

11 JUnit tests — 7 Spring Boot integration tests running against a live PostgreSQL
service container in GitHub Actions CI, plus 4 unit tests covering the distance
calculation and edge cases.

**Stack:** Java 21 · Spring Boot 3 · Spring Data JPA · PostgreSQL · React · Docker

---

## Open Source

Seven upstream pull requests to [SevenTV](https://github.com/SevenTV/Extension),
a browser extension with 2M+ daily users across Twitch, Kick and YouTube —
repairing element selectors broken by platform UI changes, fixing a DOM mount
race on the video stats icon, and suppressing debug logging in production builds.
TypeScript · Vue.

---

## Currently

- Open to junior and graduate software engineering roles — Dublin or remote
- Learning Kotlin and Android

---

danielclarke627@gmail.com · [LinkedIn](https://linkedin.com/in/dc-clarke)
