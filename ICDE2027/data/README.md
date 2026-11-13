# ICDE 2027 evaluation data

This directory contains 1,600 benchmark queries across eight subsets. Each JSONL
file contains 200 queries with their supplied contexts and gold annotations.
Evaluation code should use the gold annotations for scoring and, in the
Condition-Given setting, supply the single resolving condition for that call.

| File | Upstream source | Source details |
| --- | --- | --- |
| `sec.jsonl` | [SEC Financial Statement Data Sets](https://www.sec.gov/data-research/sec-markets-data/financial-statement-data-sets) | SEC filing-derived financial metrics. |
| `tatqa.jsonl` | [TAT-QA](https://github.com/NExTplusplus/TAT-QA) | Evidence reconstructed from the official train and dev tables and paragraphs. |
| `retail.jsonl` | [UCI Online Retail II](https://archive.ics.uci.edu/dataset/502/online+retail+ii) | Online Retail II transaction workbook. |
| `ambigdocs.jsonl` | [AmbigDocs](https://ambigdocs.github.io/) | Development split. The source-reviewed builder expects `dev.json`. |
| `opinionqa.jsonl` | [OpinionQA](https://github.com/tatsu-lab/opinions_qa) | OpinionQA data based on the Pew American Trends Panel. |
| `usc.jsonl` | [United States Code](https://uscode.house.gov/download/download.shtml) | Statute text. Use the cited provisions in the benchmark metadata. |
| `sf311.jsonl` | [DataSF 311 Cases](https://data.sf.gov/City-Infrastructure/311-Cases/vw6y-z8j6) | Archived SF311 case extract. The live source may change. |
| `nyc311.jsonl` | [NYC Open Data 311 Service Requests](https://data.cityofnewyork.us/Social-Services/311-Service-Requests-from-2020-to-Present/erm2-nwe9/about_data) | The builder expects the 2026-10-08 CSV export and selects dates from 2024-02-01 inclusive to 2024-12-01 exclusive. |

For evaluation, use the supplied JSONL files. The upstream sources are relevant
when rebuilding subsets. Consult the original data providers for their terms.
Source landing pages can serve newer snapshots than the construction inputs.

## Input verification

The seven inputs other than TAT-QA match the canonical record hashes in a saved
multimodel run audit. TAT-QA is the evidence-reconstructed input from the
dedicated five-model runner package. Its 200 IDs, query hashes, and gold hashes
match that runner's reference. `manifest.tsv` records counts and SHA-256 hashes
for these distributed files.

The archived multimodel runner in Package 02 covers seven subsets. TAT-QA uses a
separate runner, provided in [TATQA_five_models.zip](../TATQA_five_models.zip).
The old 610-query TAT-QA file in Package 02 belongs to an earlier setup.
Verification here covers input provenance and the TAT-QA dry run. Full
paper-table reproduction requires the corresponding run configurations and
scoring outputs.
