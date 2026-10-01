# Supporting Materials

Supporting material for the FYP (CT-CLIP-based chest CT abnormality detection project). This repo is **not application code** — it holds the notebooks used to test models and generate evidence that the team uses to make decisions (preprocessing choices, model/backbone selection, and diagnosing results such as low accuracy or a domain gap between local and public scans). Only the notebooks (and this README) are version-controlled here; their outputs (PDF reports, CSVs, figures) are produced locally when the notebooks are run and are not committed.

## Notebooks

- **`CT_CLIP_Inference_Test.ipynb`** — Runs CT-CLIP zero-shot inference on local DICOM chest CTs: predicts the 18 CT-RATE abnormality labels, records time/RAM/VRAM per stage (including a CPU-only run), and evaluates against RadBERT report-derived labels and a public CT-RATE reference sample. Used to decide whether CT-CLIP's predictions and preprocessing pipeline are correct, and to diagnose accuracy issues.
- **`CT_Domain_Gap_Analysis.ipynb`** — Compares local scans against public CT-RATE and LIDC-IDRI scans using image statistics and three feature extractors (CT-CLIP, DALE-CT-0, CT-FM): novelty/distribution tests, UMAP maps, yardsticks (e.g. unseen-vendor, same-scan-different-kernel), and controls with known degradations. Used to decide whether a domain gap exists, how large it is, and which backbone generalizes best for further work.

## How these feed decisions

Both notebooks are diagnostic, not production code: they are re-run as new scans or models become available, and their outputs are read by the team before deciding on preprocessing steps (e.g. kernel/noise harmonization) and backbone/model choices for the main pipeline.
