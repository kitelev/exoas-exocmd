---
exo__Asset_isDefinedBy: "[[60967c6a-4e8a-4ee3-8922-db98b981e4f4]]"
exo__Asset_uid: 00a6a887-1df8-4bc9-b9be-bc32c1ca9efb
exo__Asset_createdAt: 2026-05-03T12:20:00
exo__Asset_updatedAt: 2026-05-24T18:40:00
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
exocmd__Grounding_inheritanceRule:
  - "[[3f08f5a8-df11-47e7-8519-7d8d84175951]]"
  - "[[43731bae-78cb-4ffe-9eaa-4c258cb1c493]]"
  - "[[cbe000c4-b29a-4405-876d-790fb2296121]]"
exocmd__Grounding_propertyDefault:
  - "[[d9aa9bb8-5676-4ba2-ba5e-fc8d9df02250]]"
exocmd__Grounding_prefillLabelWithDate: true
---

# Create ProjectPrototype instance

Grounding для создания `ems__Project` instance из `ems__ProjectPrototype`.

- `Grounding_type=create_instance` → `GroundingExecutor.executeCreateInstance`.
- `targetClass=ems__Project` → `exo__Instance_class: [[7db5eeff-718a-49b0-8d2b-39b084a356e3]]` в новом файле.
- `targetPrototype=b2a49bb7-...|ems__ProjectPrototype` → `exo__Asset_prototype: [[...]]` в новом файле.
- `targetFolder=03 Knowledge/inbox` — место создания файла.
- `inputSchema` — modal с полем label (Project name).

ProjectPrototype variant of Create Instance Command (`[[bb00efed-7b17-42f5-a2c4-7cadf3e0ab36]]`).
