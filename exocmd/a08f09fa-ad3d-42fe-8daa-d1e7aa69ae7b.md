---
exo__Asset_uid: a08f09fa-ad3d-42fe-8daa-d1e7aa69ae7b
exo__Asset_label: "Complete → Action binding"
exo__Asset_isDefinedBy: "[[60967c6a-4e8a-4ee3-8922-db98b981e4f4]]"
exo__Asset_createdAt: 2026-06-28T11:25:00
exo__Asset_updatedAt: 2026-06-28T11:40:00
exo__Instance_class:
  - "[[3677039a-a5a8-4402-9a07-f8f18fe384ad]]"
exocmd__CommandBinding_command: "[[f86925c4-b165-4a47-a941-edeaf987b746]]"
exocmd__CommandBinding_targetClass: "ems__Action"
exocmd__CommandBinding_position: "inline"
exocmd__CommandBinding_order: 130
exocmd__CommandBinding_group: "status"
---

# Complete → Action binding

Binds the "Complete" command (`f86925c4`) to `ems__Action` assets — one-tap completion for atomic actions (e.g. medication-intake actions). The command reuses the composite grounding `77be16d6` (sets `ems__Effort_status` → Done + stamps `ems__Effort_endTimestamp` + `ems__Effort_resolutionTimestamp` with the actual completion time) and the permissive precondition `37517554` (visible until Done) so an action transitions **any-status → Done in a single tap** (Backlog → Done). The button hides once the action is Done.
