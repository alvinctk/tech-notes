## Launch!

1. Get your solution ready for production (plug into production data inputs, write unit tests, etc.).

2. Write monitoring code to check your system’s live performance at regular intervals and trigger alerts when it drops.

- Beware of slow degradation: models tend to “rot” as data evolves.

- Measuring performance may require a human pipeline (e.g., via a crowdsourcing service).

- Also monitor your inputs’ quality (e.g., a malfunctioning sensor sending random values, or another team’s output becoming stale). This is particularly important for online learning systems.

[Back to Machine Learning Project Checklist](./README.md)
