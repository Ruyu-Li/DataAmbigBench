# DataAmbigBench — ICDE 2027 Reproducibility Materials

[Evaluation data and upstream sources](./data/) — 1,600 queries across eight subsets, with 200 queries per subset.

[Evaluation results](./results/) — Main evaluation scores, scalability results, token usage, and request latency.

Download and extract the ZIP package for the workflow you need.

| Goal | Package |
| --- | --- |
| Inspect dataset construction and validation | [01 — Dataset Construction and Validation](./01_Dataset_Construction_and_Validation.zip) |
| Inspect evaluation, scoring, and resume scripts | [02 — Main Evaluation, Resume and Scoring](./02_Main_Evaluation_Resume_and_Scoring.zip) |
| Inspect scalability experiments, analysis scripts, and paper assets | [03 — Scalability, Analysis and Paper Assets](./03_Scalability_Analysis_and_Paper_Assets.zip) |

Each package includes a README and a file manifest.

## Main evaluation inputs

The ICDE 2027 benchmark contains 1,600 queries across eight subsets.
The archived multi-model runner in Package 02 covers seven subsets
(1,400 queries). The 200-query TAT-QA subset uses a dedicated runner
provided in [TATQA_five_models.zip](./TATQA_five_models.zip).

The released inputs have been checked against the archived input records.
End-to-end reproduction of the full main results table is still being verified.
