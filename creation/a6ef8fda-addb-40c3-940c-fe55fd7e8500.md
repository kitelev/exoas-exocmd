---
exo__Asset_isDefinedBy: "[[60967c6a-4e8a-4ee3-8922-db98b981e4f4]]"
exo__Asset_uid: a6ef8fda-addb-40c3-940c-fe55fd7e8500
exo__Asset_createdAt: 2026-05-02T09:19:00
exo__Asset_updatedAt: 2026-05-03T12:20:00
exo__Asset_createdBy: "[[de20a3f1-7483-4714-ab28-b45f5cf02c76]]"
exo__Instance_class:
  - "[[11579feb-2e42-491c-af59-b89b1129a539]]"
exo__Asset_label: "Create TaskPrototype instance"
aliases:
  - "Create TaskPrototype instance"
exocmd__Grounding_type: "create_instance"
exocmd__Grounding_targetFolder: "03 Knowledge/inbox"
exocmd__Grounding_targetClass: "1b20a8f0-d745-4e93-91db-4531b3df120e"
exocmd__Grounding_targetPrototype: "df7e579d-02d4-4f3a-971f-3d1d785b689b"
exocmd__Grounding_inputSchema: '{"type":"object","properties":{"label":{"type":"string","title":"Task name"}},"required":["label"]}'
exocmd__Grounding_prefillLabelWithDate: true
---

# Create Task instance from prototype

Grounding для создания `ems__Task` instance из `ems__TaskPrototype`.

- `Grounding_type=create_instance` → `GroundingExecutor.executeCreateInstance`.
- `targetClass=ems__Task` → `exo__Instance_class: [[1b20a8f0-d745-4e93-91db-4531b3df120e]]` в новом файле.
- `targetPrototype=df7e579d-...|ems__TaskPrototype` → `exo__Asset_prototype: [[...]]` в новом файле.
- `targetFolder=03 Knowledge/inbox` — место создания файла.
- `inputSchema` — modal с полем label (Task name).

TaskPrototype variant of Create Instance Command (`[[bb00efed-7b17-42f5-a2c4-7cadf3e0ab36]]`).
