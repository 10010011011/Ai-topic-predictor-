# Topic Forecasting Workbench

A browser-first, configurable forecasting workbench for turning collections of question-paper PDFs into structured records, applying editable historical weights, fitting a forecasting model, and producing readable topic forecasts.

## User flow

**Input → Sorting → Config → Training → Use**

### Input
Upload one or many PDF papers. Original sources stay separate from normalized records.

### Sorting
Extract and normalize question-level records with year, date, shift, subject and topic metadata. Cleaning and deduplication happen before model fitting.

### Config
Adjust historical weights manually. A recent-data-heavy preset is supplied as the default configuration, but every year can be edited and additional years can be added later.

### Training
Fit/refit on the complete accumulated corpus using the current configuration. New years, missing shifts, or extra paper sets can be appended later and the model can be refit without throwing away older data.

### Use
Select a target date/shift and generate a user-readable forecast.

## Design goal

The forecasting layer is intentionally separate from examination-specific taxonomy and metadata rules, so the same workbench can be adapted to different exam or question-paper collections.

## Project structure

```
app/
  index.html
  app.js
  styles.css
config/
  default-weights.json
docs/
  ARCHITECTURE.md
```

## Status

The repository currently contains the privacy-neutral browser workbench shell and configuration flow. The next implementation step is wiring the full PDF extraction, structured sorting, persistent corpus, calibration, forecasting engine, and evaluation pipeline into the tabs above.

No external AI endpoint is required by the forecasting engine.
