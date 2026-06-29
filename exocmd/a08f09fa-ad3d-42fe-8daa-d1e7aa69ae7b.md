---
exo__Asset_uid: a08f09fa-ad3d-42fe-8daa-d1e7aa69ae7b
exo__Asset_label: "Execute → Action binding"
exo__Asset_isDefinedBy: "[[60967c6a-4e8a-4ee3-8922-db98b981e4f4]]"
exo__Asset_createdAt: 2026-06-28T11:25:00
exo__Asset_updatedAt: 2026-06-29T10:05:00
exo__Instance_class:
  - "[[3677039a-a5a8-4402-9a07-f8f18fe384ad]]"
exocmd__CommandBinding_command: "[[f86925c4-b165-4a47-a941-edeaf987b746]]"
exocmd__CommandBinding_targetClass: "ems__Action"
exocmd__CommandBinding_position: "inline"
exocmd__CommandBinding_order: 130
exocmd__CommandBinding_group: "status"
---

# Execute → Action binding

Binds the "Execute" command (`f86925c4`) to `ems__Action` assets — one-tap
completion for atomic actions (epic `40188c71`). Sets status → Done + stamps
`resolvedAt`. The button hides once the action is Done (precondition `37517554`).
