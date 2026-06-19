---
exo__Asset_isDefinedBy: "[[60967c6a-4e8a-4ee3-8922-db98b981e4f4]]"
exo__Asset_uid: 257a0a81-e53d-4fd8-8cfb-9babca0a2ed2
exo__Asset_createdAt: 2026-06-20T01:59:57
exo__Asset_updatedAt: 2026-06-20T01:59:57
exo__Asset_createdBy: "[[de20a3f1-7483-4714-ab28-b45f5cf02c76|ExoAssistant]]"
exo__Instance_class:
  - "[[74d6d2d3-c435-4fd0-9c4b-d9dc9f0bb088]]"
exocmd__PropertyDefault_property: "[[179d6b59-c7fc-4bdf-a32f-ace630884a8c]]"
exocmd__PropertyDefault_value: "[[8da5d721-cc48-42a8-9945-31793898fd7f]]"
exo__Asset_label: "PropertyDefault: exo__Asset_isDefinedBy = $targetClassSelf"
aliases:
  - "PropertyDefault: exo__Asset_isDefinedBy = $targetClassSelf"
---

# PropertyDefault: exo__Asset_isDefinedBy = $targetClassSelf

`exocmd__PropertyDefault` (project 85150d63, W3 «Create Class»).

Attached to the «Create Class» Grounding `12a7d3ef-bfb0-41ff-b32a-b50f1988d50c`.
Sets `exo__Asset_isDefinedBy` of the new `exo__Class` to the `$targetClassSelf`
SubstitutionToken (`8da5d721-...`) — the click-target file's own UID. The host
page IS the ontology, so the new class is defined by that host ontology.
Overrides the Universal Default Template's
`exo__Asset_isDefinedBy = $target.property(isDefinedBy)` entry by property name
(W3 wants the host ontology itself, not the host's own isDefinedBy).

Reuses the T1 «Create Instance» `$targetClassSelf` token (`8da5d721-...`); only
the bound property (`exo__Asset_isDefinedBy`, `179d6b59-...`) differs.
