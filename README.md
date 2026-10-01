# Supporting Materials

Supporting material for our FYP research. This repo is **not application code** — it holds the notebooks used to test models and generate evidence that the team uses to make decisions (preprocessing choices, model/backbone selection, and diagnosing results such as accuracy issues or a domain gap between local and public scans). Only the notebooks (and this README) are version-controlled here; their outputs (reports, CSVs, figures) are produced locally when the notebooks are run and are not committed.

## Notebooks

- **`CT_CLIP_Inference_Test.ipynb`** — Runs zero-shot abnormality-detection inference on local DICOM chest CTs and evaluates it against report-derived labels and a public reference sample. Used to decide whether the model's predictions and preprocessing pipeline are correct, and to diagnose accuracy issues.
- **`CT_Domain_Gap_Analysis.ipynb`** — Compares local scans against public reference scans using image statistics and multiple feature extractors: novelty/distribution tests, 2-D maps, yardsticks, and controls with known degradations. Used to decide whether a domain gap exists, how large it is, and which backbone generalizes best for further work.

## How these feed decisions

Both notebooks are diagnostic, not production code: they are re-run as new scans or models become available, and their outputs are read by the team before deciding on preprocessing steps and backbone/model choices for the main pipeline.
