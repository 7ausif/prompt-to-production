skills:
  - name: classify_complaint
    description: Classify a single complaint row into category, priority, reason, and flag.
    input: A dictionary or CSV row representing one complaint.
    output: A dictionary with keys category, priority, reason, and flag.
    error_handling: If the input is invalid or ambiguous, assign category "Other" and set flag to "NEEDS_REVIEW".

  - name: batch_classify
    description: Reads an input CSV, applies classify_complaint to each row, and writes the results to an output CSV.
    input: File paths to input CSV and output CSV.
    output: A new CSV file containing the original rows and classification results.
    error_handling: Flags nulls, does not crash on bad rows, and ensures output is produced even if some rows fail.
