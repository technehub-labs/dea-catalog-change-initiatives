# CR-CHI-CAT-07: Shard Subdivision (R5 Remedy — Two-Level Shards)

**Status**: Landed (this PR)
**Layer**: Catalog tooling (storage layout)
**Owner**: Emmanuel A. Otchere
**Date**: 2026-11-15
**Admission authority**: layout only (no record changes)
**Trigger**: The weekly reconciler (R5) flagged the over-cap shard directories created by this programme's corpus (slugs cluster on one letter — the corpus ids share a prefix, so first-letter shards cluster); remedy per entity-storage-layout.md §4 (CR-MET-024/metrics subdivide recipe).
**Carrier**: Single PR on feature branch `feat/cr-chi-cat-07`. PR review, not direct push.

## 1. What this CR does

1. Subdivides the over-cap shard into two-character sub-shards (every resulting directory well under the 800-entry cap).
2. Upgrades the vendored toolchain to depth-3 shard walking: `regenerate_catalog.py` + `check_catalog_index.py` (shard descent, 1–2 char alnum shard names including digits, relative-path rel-dir) and `check_contributions.py` (rglob queue walk).
3. `CATALOG.yaml` regenerated; record ids untouched.

## 2. Verification

- All gates green locally (posture/queue/schema/documentation/index `--strict`/`regen --check`).
- R5 post-merge: this repo's over-cap findings are gone.

## 3. NOT-List

- No record content changes; no ids change; no admissions.
