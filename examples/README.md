# Examples

This folder contains sample classified outputs that show how the framework can be applied to common programmatic use cases.

## Files

- `sample_classifications.jsonl`  
  One JSON object per line. Good for ML pipelines, API examples, and ingestion tests.

- `sample_classifications.tsv`  
  Tab-separated version of the same examples. Good for spreadsheet review, QA, and ad-tech data workflows.

## Notes

- These are illustrative examples, not benchmark labels.
- Real implementations should add:
  - source URL or content metadata
  - confidence calibration logic
  - mapped IAB Content / Audience / Ad Product IDs
  - policy restrictions based on market and platform
- A practical implementation should support:
  - 1 primary intent pattern
  - up to 2 secondary intent patterns
  - 1 primary domain
  - 0 to many modifiers
  - explicit stage, readiness, actionability, and confidence

## Suggested future additions

- `input_snippets/` with raw content excerpts
- `gold_labels/` for evaluation
- `policy_examples/` for sensitive vertical handling
- `bidstream_examples/` for downstream ad-tech integration
