---
exo__Asset_uid: e42f2e7c-dfab-47b9-8e7e-2edfd7a08d95
exo__Asset_label: "Mark Reviewed"
aliases:
  - "Mark Reviewed"
exo__Asset_isDefinedBy: "[[60967c6a-4e8a-4ee3-8922-db98b981e4f4]]"
exo__Asset_createdAt: 2026-05-19T13:21:52
exo__Asset_updatedAt: 2026-05-19T13:21:52
exo__Asset_createdBy: "[[de20a3f1-7483-4714-ab28-b45f5cf02c76]]"
exo__Instance_class:
  - "[[790e5b16-251d-4556-96ac-e5c7f1429b2e]]"
exocmd__Command_icon: eye-check
exocmd__Command_grounding: "[[1153261d-5763-4416-b0b8-242f0b35fe41]]"
exocmd__Command_successMessage: "Marked as reviewed"
exocmd__Command_category: status
exocmd__Command_cliName: mark-reviewed
exocmd__Command_destructive: false
---

# Mark Reviewed

Stamps `ems__Effort_reviewTimestamp` with current local timestamp on the target asset.

- **Precondition**: none (no `exocmd__Command_precondition` set — button visible on all eligible assets; can be tightened later if Done-status-only filtering is desired)
- **Grounding**: Single-step `property_set` (`1153261d`) — writes `$nowLocal` to `ems__Effort_reviewTimestamp` via UUID-wikilink targetProperty
- **Icon**: eye-check (Lucide)
- **Category**: status
- **Destructive**: false (reversible — just unset the property)

## Phase 1.5 — gap closure (RFC 31c1a0be)

Created to fill the vault-Command gap identified by Phase 0 wiring audit (kitelev/exocortex#3194 comment 4484576716):

> Legacy `MarkReviewedCommand.ts` injects `TaskStatusService.markAsReviewed`, but no vault `exocmd__Command` with `cliName: mark-reviewed` existed. Phase 4 deletion of legacy TS commands would silently lose this functionality without this gap closure.

## Runtime activation status

⚠️ **Grounding uses Phase 3 wikilink-form `targetProperty`** — pre-Phase-3 parser may not resolve at runtime. Activation deferred to Phase 3 parser PR merge. Until then, the legacy `MarkReviewedCommand.ts` TS class remains the active path (no functional regression).

After Phase 3 parser update, this vault Command becomes the canonical path; Phase 4 deletes the TS class.

## Cross-references

- Property asset: `[[65f3f5d9-3366-4a66-9c38-44016c59bc80]]` (`ems__Effort_reviewTimestamp` in `assetspaces/ems/`)
- Grounding: `[[1153261d-5763-4416-b0b8-242f0b35fe41]]`
- Legacy TS class to delete in Phase 4: `packages/obsidian-plugin/src/application/commands/MarkReviewedCommand.ts`
