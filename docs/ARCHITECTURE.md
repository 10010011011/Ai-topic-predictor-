# Architecture

The application is separated into four user-facing stages.

1. **Input** — upload PDF collections and retain source provenance.
2. **Sorting** — normalize question-level records with year/date/shift/subject/topic metadata.
3. **Config** — manually edit year and shift weights. The shipped preset is a configurable historical prior.
4. **Training** — fit/refit on the accumulated weighted corpus; new uploads can be appended later.
5. **Use** — select a target date/shift and generate a readable forecast.

Taxonomy, metadata rules and weighting defaults are configurable so the same engine can be adapted to different examination collections.