---
exo__Asset_uid: ebbaa9e4-bfc2-412a-8d7f-bd46b0f6c988
exo__Asset_label: "Has empty properties, not archived, and visible until terminal"
exo__Asset_isDefinedBy: "[[60967c6a-4e8a-4ee3-8922-db98b981e4f4]]"
exo__Asset_createdAt: 2026-07-07T22:22:00
exo__Asset_updatedAt: 2026-07-07T22:22:00
exo__Instance_class:
  - "[[dd42b973-5943-400b-b580-f2a1e539dd60]]"
exocmd__AllPrecondition_preconditions:
  - "[[7ea05611-0325-4368-802e-71fd3afc5c7c]]"
  - "[[067e481d-ba2e-4022-a4ec-9e7741a0b7af]]"
---

# Has empty properties, not archived, and visible until terminal

**AllPrecondition** wrap-the-wrapper for **«Clean Properties»** (`0da175e1`) —
req(ems) `127763f8` (Trashed is a second terminal status equal to Done). AND of:
1. [[7ea05611-0325-4368-802e-71fd3afc5c7c|Has empty properties, not archived, and visible until Done]] — the shipped utility-status-gate composite (req `f6c2b98c`), **unchanged**; AND
2. [[067e481d-ba2e-4022-a4ec-9e7741a0b7af|Visible until terminal (not Done, not Trashed)]] — hides «Clean Properties» once the effort is terminal (Done **or** Trashed).

Nests the already-shipped composite one level deeper (wrap-the-wrapper — the
utility-gate composite is **not** mutated) and «Clean Properties» is repointed
here. Net effect: hidden on Done **and** on Trashed; behavior-preserving on
Backlog/Doing.
