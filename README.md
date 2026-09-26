# Topic Forecasting Workbench

A browser-first, configurable forecasting workbench for extracting structured question data from PDF collections, applying year/shift weighting, fitting a forecasting model, and generating readable topic forecasts.

## Pipeline

1. Input PDF files.
2. Sort and normalize the extracted data into structured records with year, date, shift, subject, chapter/topic fields, and provenance.
3. Review or edit manual year/shift weights. A configurable historical-weight preset is supplied as the default; all weights remain editable.
4. Train/refit the forecasting model.
5. Use the trained model to generate forecasts.

The system is designed so the same pipeline can be adapted to different examinations or question-paper collections by replacing the taxonomy and default weighting configuration.

## Planned interfaces

- **Input**: PDF upload, extraction, segmentation, metadata detection, deduplication.
- **Config**: taxonomy, year/shift weights, recency settings, forecast horizon, model controls.
- **Training**: corpus validation, fit/refit, calibration, evaluation, model versioning.
- **Use**: target date/shift selection and user-readable forecast output.

## Data principles

- Original PDFs remain separate from normalized records.
- New years or missing shifts can be appended later.
- Retraining/refitting uses the accumulated corpus rather than only the newest upload.
- Configuration is explicit and versioned so historical experiments remain reproducible.
- No external AI endpoint is required for the forecasting engine.

## Current status

This repository is an initial shell. The full browser application and local extraction/forecasting implementation will be added in follow-up commits.
