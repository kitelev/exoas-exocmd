---
exo__Asset_isDefinedBy: "[[60967c6a-4e8a-4ee3-8922-db98b981e4f4]]"
exo__Asset_uid: bb00efed-7b17-42f5-a2c4-7cadf3e0ab36
exo__Asset_createdAt: 2026-04-27T21:31:58
exo__Instance_class:
  - "[[790e5b16-251d-4556-96ac-e5c7f1429b2e]]"
exo__Asset_label: Create Task Instance
aliases:
  - Create Task Instance
exocmd__Command_icon: plus-square
exocmd__Command_category: creation
exocmd__Command_grounding:
  - "[[a6ef8fda-addb-40c3-940c-fe55fd7e8500]]"
  - "[[00a6a887-1df8-4bc9-b9be-bc32c1ca9efb]]"
  - "[[e01b025b-d03f-4028-b4c8-45d3786ff43d]]"
  - "[[3da98088-3d29-40fe-9947-9404d51d7c28]]"
  - "[[adc73790-d984-4365-bec5-a19e114c1a83]]"
  - "[[2f8db9d5-bde4-4242-889d-a85d17ce870f]]"
exocmd__Command_confirmMessage: Create a new task from this prototype?
exocmd__Command_successMessage: Task instance created
exocmd__Command_cliName: create-task-instance
exocmd__Command_destructive: true
exo__Asset_updatedAt: 2026-05-26T10:57:43+0500
---

# Create Instance

Universal "Create Instance" command для prototype-based asset creation. Modal prompts label → new asset created в `targetFolder` с `exo__Instance_class=targetClass` и `exo__Asset_prototype=targetPrototype` (через `GroundingType.CREATE_INSTANCE` executor, см. `services/GroundingExecutor.ts:425-473`).

## Description

Visible на любом asset, чей class имеет prototype lineage (`canCreateInstance` predicate per audit C.1.1). Click → modal labels → instance file created.

## Grounding assets (C.1.3 — completed)

N=5 groundings с `type=create_instance` (RF-016):

| Prototype | Grounding | instanceClass |
|-----------|-----------|---------------|
| ems__TaskPrototype | `[[a6ef8fda-addb-40c3-940c-fe55fd7e8500]]` | ems__Task |
| ems__ProjectPrototype | `[[00a6a887-1df8-4bc9-b9be-bc32c1ca9efb]]` | ems__Project |
| ems__MeetingPrototype | `[[e01b025b-d03f-4028-b4c8-45d3786ff43d]]` | ems__Meeting |
| ztlk__FleetingNotePrototype | `[[3da98088-3d29-40fe-9947-9404d51d7c28]]` | ztlk__FleetingNote |
| exo__EventPrototype | `[[adc73790-d984-4365-bec5-a19e114c1a83]]` | exo__Event |

## Implementation roadmap

- **Grounding** (`exocmd__Command_grounding`) — ✅ C.1.3 done. N=5 groundings с `create_instance` type.
- **Precondition** (`exocmd__Command_precondition`) — predicate-based visibility filter. Будет добавлено в C.1.4.
- **Bindings** — per-prototype `exocmd__CommandBinding` ассеты с разными `targetClass`. Будут созданы в C.1.4.

## Notes

- Pattern: один Command + N Grounding (per `Grounding_targetPrototype`) + N Bindings (per `targetClass`).
- Constraint: нет `$instanceClass`/`$prototypeIRI` token interpolation в `GroundingExecutor` → отдельный Grounding для каждого prototype value.
- Category `creation` группирует с Create Task (`dec97198-…`), Create Project (`3520c214-…`).

## Related

