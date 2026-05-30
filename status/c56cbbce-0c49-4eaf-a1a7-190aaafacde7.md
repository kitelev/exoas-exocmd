---
exo__Asset_uid: c56cbbce-0c49-4eaf-a1a7-190aaafacde7
exo__Asset_label: "Rollback Doing→Backlog (composite)"
exo__Asset_isDefinedBy: "[[60967c6a-4e8a-4ee3-8922-db98b981e4f4]]"
exo__Asset_createdAt: "2026-05-30T17:10:00"
exo__Instance_class:
  - "[[11579feb-2e42-491c-af59-b89b1129a539]]"
exocmd__Grounding_type: "[[8f9a57db-3865-4886-92fb-c5ab7f3c3fa3]]"
exocmd__Grounding_steps:
  - "[[cfd2d68a-49cc-4a9f-9231-abd3dece59fb]]"
  - "[[1a14832c-f657-4816-b2aa-d06f2a80fccf]]"
---

# Rollback Doing→Backlog (composite)

Composite grounding for rolling back a Task from Doing → Backlog:

1. Set `ems__Effort_status` → `[[753a44d5-846c-4b82-9196-4fd9a4d48777]]` (Backlog)
2. Delete `ems__Effort_startTimestamp`

Atomic via `GroundingExecutor.executeComposite` rollback on step failure. Used by command "Rollback to Backlog" for `ems__Task`.
