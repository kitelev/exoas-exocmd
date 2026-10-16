---
exo__Asset_uid: 38cc7bec-16c4-4aed-99fa-aaa2a2a601b9
exo__Asset_createdAt: 2026-10-16T21:11:55
exo__Asset_updatedAt: 2026-10-16T21:12:32
exo__Instance_class:
  - "[[790e5b16-251d-4556-96ac-e5c7f1429b2e]]"
exo__Asset_createdBy: "[[4ef3962d-b8a7-42b5-bd28-88ec846f1d13]]"
exo__Asset_label: Remove Aliases from Archived
aliases:
  - Remove Aliases from Archived
exo__Asset_isDefinedBy: "[[60967c6a-4e8a-4ee3-8922-db98b981e4f4]]"
exocmd__Command_cliName: remove-aliases-from-archived
exocmd__Command_precondition: "[[6df99221-7339-4c51-8c4a-e45f269ca48b]]"
exocmd__Command_grounding: "[[f7ff115b-60e2-451b-ba8a-3e0a61745e80]]"
exocmd__Command_successMessage: Aliases removed
exocmd__Command_category: misc
exocmd__Command_icon: trash
exocmd__Command_destructive: true
---
# Remove Aliases from Archived

Removes ALL aliases (`exo__Asset_aliases`) from an archived asset.

**Precondition** — shown only when the asset is archived AND has at least one alias:
- `exo__Asset_archived \true\`
- `exo__Asset_aliases ?alias`

**Grounding** — a single `property_delete` step (type `4bdf1d0b`) on `aliases`, the delete-side counterpart of the «Copy Label to Aliases» / «Set Label» re-mirror step (#3798).

Supports the rule: *archived assets must not carry aliases* (aliases are for Command+O search on live assets only).
