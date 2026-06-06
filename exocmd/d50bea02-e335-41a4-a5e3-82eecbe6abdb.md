---
exo__Asset_isDefinedBy: "[[60967c6a-4e8a-4ee3-8922-db98b981e4f4]]"
exo__Asset_uid: d50bea02-e335-41a4-a5e3-82eecbe6abdb
exo__Asset_createdAt: 2026-05-21T23:13:28
exo__Asset_updatedAt: 2026-05-21T23:13:28
exo__Instance_class:
  - "[[30d63ce4-e574-456c-8de8-2bf1a53688c1]]"
exo__Property_domain: "[[08cec529-90eb-4d43-88de-ceecccea12b0]]"
exo__Property_description: Literal string name SubstitutionToken (без $ prefix). Cardinality 1. UNIQUE constraint — Phase 1 bootstrap делает SPARQL lookup перед create.
exo__Asset_label: exocmd__SubstitutionToken_name
aliases:
  - exocmd__SubstitutionToken_name
exo__Property_displayName: tokenName
---

# exocmd__SubstitutionToken_name

`exo__StringProperty` on `exocmd__SubstitutionToken`. Cardinality 1. **Unique constraint.**

YAML serialization:
```yaml
exocmd__SubstitutionToken_name: today
```

Engine при scan `$<name>` в `PropertyDefault_value` text — match by trailing `_name` value. Если duplicate names — first wins; idempotency check (Phase 1 bootstrap + future migration) предотвращает duplicates.

Bootstrap names (Phase 1): `today`, `todayStart`, `targetFolder`, `target`.
