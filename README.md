# Cass-V Lite RSI Demo Run

Original project: https://github.com/uberbestest/Cass-V-Lite

This repository is a public artifact for a bounded RSI-style demo run on Cass-V Lite.
It does not contain Cass-V Lite source code and is not a reconstructed copy of the
main project.

## What This Demonstrates

The run tested whether Codex could preserve a frozen baseline while allowing exactly
one bounded, test-only improvement.

The approved mutation was limited to one file in the original project:

- `test_cass_v_lite.py`

The forbidden changes were:

- no `cass_v_lite.py` edits
- no README edits in the original project
- no example edits
- no source-file creation
- no behavior reconstruction
- no opportunistic cleanup
- no formatting-only expansion outside the test addition

## Contents

- `rsi-run-ledger.md`: structured run record, including freeze, mutation budget,
  checks, accepted delta, and residual risks.
- `substack-draft.md`: readable public writeup draft for the run.
- `verification-notes.md`: commands and observed verification results.
- `dirty-test_cass_v_lite-before-clean-freeze.patch`: preserved patch containing
  the approved test-only delta.

## Result

The preserved patch touches only `test_cass_v_lite.py`. It adds a CLI argument text
regression test and requires no source changes to pass.

Verification result:

```text
python -B -m unittest
Ran 6 tests ... OK
```

## Boundary

This repository is the demo/run artifact. The decision to commit the test-only delta
back to the original Cass-V Lite repository is intentionally separate.
