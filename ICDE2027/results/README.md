# ICDE 2027 results

| Results | Files |
| --- | --- |
| Main evaluation | [ICDE 2027 benchmark scores](./main/main_evaluation_icde2027.csv) and [DeepSeek results on the earlier benchmark](./main/deepseek_earlier_benchmark.csv) |
| Scalability | [Hinted E2E accuracy, valid response counts, and request latency by table size](./scalability/scalability_summary.csv) |
| Efficiency | [Token usage and request latency by model and task](./efficiency/efficiency_by_model_task.csv), [breakdown by subset](./efficiency/efficiency_by_model_dataset_task.csv), and [run coverage](./efficiency/source_coverage.csv) |

## Main evaluation

The CSVs transcribe the detailed Table II source in
`paper/table_ii_deepseek_revision/table2_detailed_results.tex` in Package 03.
The ICDE CSV contains six models on all eight subsets plus the DeepSeek
NYC311 Geography result. The earlier DeepSeek evaluation has its own CSV.
Values are percentages at the precision of the table source. Empty cells
in the earlier results denote unavailable values. On NYC311 Geography,
the exact/normalized and relaxed/normalized Hinted E2E columns use the
original and revised Geography scorers, respectively. For Online Retail II,
Open Answer-Only Recall uses the scoring reported for Figure 3.

## Scalability

The CSV covers 18 settings, with three models and three nominal table sizes
for each of Online Retail II and SF311. Each setting planned 200 queries.
Reported accuracy and latency use the valid JSON responses from successful
requests, deduplicated by dataset, model, nominal table size, and query.
Accuracy is the mean relaxed-answer score under normalized interpretation
matching. Latency is reported in seconds, with the median for P50 and
nearest-rank P95. All 18 rows match the archived ICDE scalability table.

In Package 03, the prediction logs and input audit are under
`scalability/table_v_outputs/`. The scaling and parallel runner scripts
are under `scalability/dual_200/` and `scalability/colab_and_parallel/`.

## Efficiency

The CSVs cover 54,476 recorded final task requests. Of those, 54,474 have
token usage and latency measurements. Five models cover eight subsets in
this archive. GPT-4.1 mini covers seven subsets in the efficiency records.
The request latency values measure observed API request durations in seconds.
