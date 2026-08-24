# Jarvi3: Themis-G ProgramBench Two-Solve Submission

This is the strict cleanroom package for `Jarvi3: Themis-G`.

It contains only instances that satisfy both gates used before publication:

- every recorded test result is `passed`;
- the sealed archive passes the local integrity scan with no sidecar binary,
  harness override, golden-answer reader, fixture hardcoding, or source
  transplant finding.

## Included instances

- `abishekvashok__cmatrix.5c082c6` - 769/769 passed
- `ajeetdsouza__zoxide.67ca1bc` - 577/577 passed

The package intentionally does not include the older five-solve artifact's
three disputed instances. This keeps the public score aligned with the
evidence that can be defended from a clean submission archive.

## Verification

The package contains the official per-test score map in `_stats/score.json`,
the light and heavy eval records, and the sealed `submission.tar.gz` archive
for each instance. The local integrity command is:

```powershell
$env:PYTHONPATH=(Resolve-Path .)
.\.venv-swebench\Scripts\python.exe -m benchmarks.programbench_integrity_scan `
  --reports docs\public_benchmark\programbench_2solve_cleanroom_v2\20260824_dtl-supermath-2solve-cleanroom-v2 `
  --show-clean
```

The leaderboard score is recomputed by the ProgramBench registry from the
included score map and its current ignored-test policy.
