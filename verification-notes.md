# Verification Notes

Original project: https://github.com/uberbestest/Cass-V-Lite

## Pre-Push Gate

1. Do not alter Cass-V Lite source behavior.
2. Do not create or reconstruct source files.
3. New GitHub repo should contain only demo/run materials.
4. If including the approved test mutation, clearly mark it as a test-only delta.
5. No secrets, tokens, local absolute-path dependency, or private architecture.
6. Link to the original Cass-V-Lite repo at the top.
7. Final local check before push:
   - `git status`
   - `git diff --name-only`
   - `python -B -m unittest`

## Patch Gate

Patch file:

- `dirty-test_cass_v_lite-before-clean-freeze.patch`

Observed patch scope:

```text
15	1	test_cass_v_lite.py
```

The patch touches exactly one file:

- `test_cass_v_lite.py`

It adds CLI argument text regression coverage and requires no source edits.

## Original Project Checks

Before applying the approved patch, the original project was restored to clean
baseline commit:

```text
5c208c04354c7229bd4edfc1553c5efdd97c88ce
```

Clean baseline verification:

```text
python -B -m unittest
Ran 5 tests ... OK
```

After applying the approved test-only patch:

```text
git diff --name-only
test_cass_v_lite.py
```

Verification:

```text
python -B -m unittest
Ran 6 tests ... OK
```

## July 3, 2026 Recheck

The original Cass-V Lite `main` branch was rechecked after the demo artifact was
created. The approved one-file `test_cass_v_lite.py` delta was already present on
`main` as:

```text
d691600 Add CLI argument text regression test
```

The artifact repository remains evidence-only and intentionally excludes Cass-V Lite
source files.

## Artifact Repo Checks

Expected artifact repo contents:

```text
README.md
rsi-run-ledger.md
substack-draft.md
verification-notes.md
dirty-test_cass_v_lite-before-clean-freeze.patch
```

The artifact repo intentionally excludes Cass-V Lite source files.
