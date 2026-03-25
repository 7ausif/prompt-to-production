skills:
  - name: classify_complaint
    description: Classifies a single complaint according to the strict taxonomy.
    input: one complaint row in
    output: category + priority + reason + flag out
    error_handling: Set flag to NEEDS_REVIEW when category is genuinely ambiguous or unable to be determined.

  - name: batch_classify
    description: reads input CSV, applies classify_complaint per row, writes output CSV
    input: input CSV file path and output CSV file path
    output: results CSV file
    error_handling: Flag nulls, do not crash on bad rows, produce output even if some rows fail.
