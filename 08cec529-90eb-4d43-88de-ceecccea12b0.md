---
exo__Asset_isDefinedBy: "[[60967c6a-4e8a-4ee3-8922-db98b981e4f4]]"
exo__Asset_uid: 08cec529-90eb-4d43-88de-ceecccea12b0
exo__Asset_createdAt: 2026-05-21T23:11:18
exo__Asset_updatedAt: 2026-05-21T23:11:18
exo__Asset_createdBy: "[[de20a3f1-7483-4714-ab28-b45f5cf02c76]]"
exo__Instance_class:
  - "[[8619c4fc-64f1-4869-b17e-e34186cacca9]]"
exo__Class_superClass:
  - "[[5ac2ff43-62b7-4316-af84-a731c3cadf7c]]"
exo__Class_description: "Named substitution variable ($today, $todayStart, $targetFolder, $target). Заменяет TS-string-based registry в GroundingExecutor.substituteVariables. Vocabulary (какие токены существуют) — RDF; resolver implementation — TS под Q3 «ядро обработки»."
exo__Asset_label: exocmd__SubstitutionToken
aliases:
  - exocmd__SubstitutionToken
---

# exocmd__SubstitutionToken

Named substitution variable used in `PropertyDefault_value` and other dynamic-substitution slots.

## Properties (Phase 1)

- `exocmd__SubstitutionToken_name` — literal string name без `$` префикса (e.g. `"today"`). Range: xsd:string. Cardinality 1. **Unique constraint.**
- `exocmd__SubstitutionToken_resolver` — engine identifier (e.g. `"today"`). Engine map'ит resolver-id → TS function. Range: xsd:string. Cardinality 1.

## Bootstrap instances (Phase 1)

- `SubstitutionToken(name="today", resolver="today")` — UTC `YYYY-MM-DD`
- `SubstitutionToken(name="todayStart", resolver="todayStart")` — ISO datetime start-of-day
- `SubstitutionToken(name="targetFolder", resolver="targetFolder")` — string substituted from target's folder path
- `SubstitutionToken(name="target", resolver="target")` — wikilink-string `[[<targetIRI>]]`

## Использование

```yaml
exocmd__PropertyDefault_value: "[[<today-token-UID>]]"
```

Engine при resolve видит range = SubstitutionToken → invoke resolver-id → substitute string.

## Idempotency

Idempotency key (Phase 1 bootstrap): unique `_name`. SPARQL lookup перед create — `?t exocmd:SubstitutionToken_name "today"`. Если non-empty → reuse existing.

## Reference

RFC v2 `2f3f640b-c5e0-4873-8c56-c390b8402cfa` § Новые классы / SubstitutionToken.
