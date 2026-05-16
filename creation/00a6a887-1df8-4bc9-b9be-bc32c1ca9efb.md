---
exo__Asset_isDefinedBy: "[[60967c6a-4e8a-4ee3-8922-db98b981e4f4]]"
exo__Asset_uid: 00a6a887-1df8-4bc9-b9be-bc32c1ca9efb
exo__Asset_createdAt: 2026-05-03T12:20:00
exo__Asset_updatedAt: 2026-05-03T12:20:00
exo__Asset_createdBy: "[[de20a3f1-7483-4714-ab28-b45f5cf02c76|ExoAssistant]]"
exo__Instance_class:
  - "[[11579feb-2e42-491c-af59-b89b1129a539]]"
exo__Asset_label: "Create ProjectPrototype instance"
aliases:
  - "Create ProjectPrototype instance"
exocmd__Grounding_type: "create_instance"
exocmd__Grounding_targetFolder: "03 Knowledge/inbox"
exocmd__Grounding_targetClass: "ems__Project"
exocmd__Grounding_targetPrototype: "b2a49bb7-3a0f-4984-aa18-38832dc967bc|ems__ProjectPrototype"
exocmd__Grounding_inputSchema: '{"type":"object","properties":{"label":{"type":"string","title":"Project name"}},"required":["label"]}'
---

# Create ProjectPrototype instance

Grounding для создания `ems__Project` instance из `ems__ProjectPrototype`.

- `Grounding_type=create_instance` → `GroundingExecutor.executeCreateInstance`.
- `targetClass=ems__Project` → `exo__Instance_class: [[ems__Project]]` в новом файле.
- `targetPrototype=b2a49bb7-...|ems__ProjectPrototype` → `exo__Asset_prototype: [[...]]` в новом файле.
- `targetFolder=03 Knowledge/inbox` — место создания файла.
- `inputSchema` — modal с полем label (Project name).

ProjectPrototype variant of Create Instance Command (`[[bb00efed-7b17-42f5-a2c4-7cadf3e0ab36|Create Instance]]`).
