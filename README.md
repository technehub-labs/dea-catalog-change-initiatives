# dea-catalog-change-initiatives

> DEA catalog for **Change Initiative** — OpenDEAM v0.3.0 (ADR-0003).

## Change Initiative (`CHI`)

- **Entity id:** `dea:entity-change-initiative`
- **Allocation:** L3 · L3-people-skills-culture
- **Status:** proposed

A deliberate effort to shift Skills, Roles, or culture within an Organizational Unit, typically funded by an Investment Initiative.

## Relationships (from the OpenDEAM model)

- **CHI → OU** — targets (dependency, 0..N:0..N)
- **CHI → II** — funded by (governance, 0..N:0..1)

## Allocation contract

This repo's `metamodel-pointer.yaml` is validated in CI against the pinned
OpenDEAM root model (`v0.3.0`) via the reusable
`validate-against-model.yml` workflow. Drift fails CI.

Content (entity instances) lands when the entity promotes from
`proposed` to `planned`/`scaffold` per the model lifecycle.

## License

Apache 2.0 — see [LICENSE](./LICENSE) and [NOTICE](./NOTICE).
