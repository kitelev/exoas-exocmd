---
exo__Asset_uid: a08f09fa-ad3d-42fe-8daa-d1e7aa69ae7b
exo__Asset_label: "Mark Done → Action binding"
exo__Asset_isDefinedBy: "[[60967c6a-4e8a-4ee3-8922-db98b981e4f4]]"
exo__Asset_createdAt: 2026-06-28T11:25:00
exo__Asset_updatedAt: 2026-06-28T11:25:00
exo__Instance_class:
  - "[[3677039a-a5a8-4402-9a07-f8f18fe384ad]]"
exocmd__CommandBinding_command: "[[923520d1-1892-4a6c-88ea-9552250a7cbe]]"
exocmd__CommandBinding_targetClass: "ems__Action"
exocmd__CommandBinding_position: "inline"
exocmd__CommandBinding_order: 130
exocmd__CommandBinding_group: "status"
---

# Mark Done → Action binding

Binds the "Mark Done" command (`923520d1`) to `ems__Action` assets — one-tap completion for atomic actions (e.g. medication-intake actions). Composite grounding sets `ems__Effort_status` → Done + stamps `ems__Effort_endTimestamp` + `ems__Effort_resolutionTimestamp` with the actual completion time. Precondition (`577f798f`) hides the button once the action is Done.
