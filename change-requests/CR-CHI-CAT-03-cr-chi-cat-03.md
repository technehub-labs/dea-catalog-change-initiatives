# CR-CHI-CAT-03: ChangeInitiative Candidate Corpus

**Status**: Landed (this PR)
**Layer**: Catalog content (candidate corpus intake)
**Owner**: Emmanuel A. Otchere
**Date**: 2026-11-15
**Admission authority**: candidate corpus only (canonical admission remains the evidence-gated step; FOUNDATIONS D-4/D-5)
**Trigger**: Skeleton-advance wave (2026-11 owner directive): advance the remaining kit skeletons with evidence-backed candidate corpora through the gated intake workflow, grounded in the metamodel projection of this catalogue. the World Bank Documents & Records API (Project Documents collection) is the candidate seed source named per FOUNDATIONS §7; change_scope=structure is a provisional default.
**Carrier**: Single PR on feature branch `feat/cr-chi-cat-03`. PR review, not direct push.
**Lands against**: `main`
**Depends on**: CHI-CAT-02 (ingestion groundwork).

## 1. What this CR lands

**999 ChangeInitiative candidate submissions** in `contributions/queue/<shard>/<slug>.yaml` from 1 evidence bank(s):

| Bank | Source | Records |
|---|---|---|
| worldbank-project-documents.json | World Bank Documents & Records API (Project Documents collection) | 999 |

Provenance in `ingestion/manifest.yaml` (bank sha256s, source URLs, retrieval dates, mapping note). Every submission carries `source_ref`, a `published-document` evidence citation, and published description prose. Provisional field mappings are documented per record and in the manifest; per-organization values are canonical-admission decisions.


## 2. What changes

- `contributions/queue/<shard>/` — 999 intake submissions (`status: queued`)
- `ingestion/manifest.yaml` — corpus provenance record (new)
- No `CATALOG.yaml` change (queue ≠ index)
- This CR file and the index row

## 3. Verification

- `check_contributions.py`: CONFORMANT (999 queue files)
- No directory holds 800+ entries (slug-prefix distribution)
- Spot-checks: records trace to their published source identifiers

## 4. NOT-List

- NOT record admission (nothing under `entities/` changes; admission follows in CHI-CAT-04+).
- NOT a modification of gates, schemas, or intake tooling.
- NOT an authoritative assessment of provisional mapped values.

## 5. Acceptance criteria

1. 999 gate-CONFORMANT submissions; manifest carries bank sha256s + source URLs.
2. Submissions carry no `id`; `status: queued`; `submitted_by: Emmanuel A. Otchere`.
3. `CATALOG.yaml` counts unchanged.
