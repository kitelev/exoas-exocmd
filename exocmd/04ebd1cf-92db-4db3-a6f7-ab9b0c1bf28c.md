---
exo__Asset_uid: 04ebd1cf-92db-4db3-a6f7-ab9b0c1bf28c
exo__Asset_createdAt: 2026-10-16T22:10:10
exo__Asset_updatedAt: 2026-10-16T23:29:16
exo__Instance_class:
  - "[[3677039a-a5a8-4402-9a07-f8f18fe384ad]]"
exo__Asset_createdBy: "[[4ef3962d-b8a7-42b5-bd28-88ec846f1d13]]"
exo__Asset_label: Remove Aliases from Archived → exo__Asset binding
aliases:
  - Remove Aliases from Archived → exo__Asset binding
exo__Asset_isDefinedBy: "[[60967c6a-4e8a-4ee3-8922-db98b981e4f4]]"
exocmd__CommandBinding_command: "[[38cc7bec-16c4-4aed-99fa-aaa2a2a601b9]]"
exocmd__CommandBinding_targetClass: exo__Asset
exocmd__CommandBinding_position: inline
exocmd__CommandBinding_order: 47
exocmd__CommandBinding_group: status
---
# Remove Aliases from Archived → exo__Asset binding

Binds the «Remove Aliases from Archived» command (`38cc7bec`) to `exo__Asset` (base class) as an inline button. Every asset page carries the button, gated at runtime by the command precondition (`6df99221`: archived AND has aliases). Sits in the `status` group.
