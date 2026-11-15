# CR-CHI-CAT-08: Shard Re-spread (R5 Remedy — slug-tail sub-shards)

**Status**: Landed (this PR)
**Layer**: Catalog tooling (storage layout)
**Owner**: Emmanuel A. Otchere
**Date**: 2026-11-15
**Admission authority**: layout only (no record changes)
**Trigger**: The reconciler (R5) flagged the sub-shard created by the first subdivision — the corpus ids share a degenerate prefix (World Bank doc ids 'd4…', ClinicalTrials NCT ids 'nc…'), so a 2-char prefix sub-shard clustered 994–1,200 entries. Remedy: re-spread entries by the SLUG TAIL (last two characters), which distributes uniformly for sequential-id corpora; per entity-storage-layout.md §4.
**Carrier**: Single PR on feature branch `feat/cr-chi-cat-08`. PR review, not direct push.

## 1. What this CR does

1. Re-spreads the degenerate sub-shard entries by slug tail (every resulting directory well under the 800-entry cap).
2. `CATALOG.yaml` regenerated; record ids and record content untouched (paths change; the index regenerates).
3. Depth-3 shard walking (landed with the subdivision CR) already handles the layout.

## 2. Verification

- All gates green locally; R5 post-merge: this repo's over-cap findings are gone.

## 3. NOT-List

- No record content changes; no ids change; no admissions; no gate changes.
