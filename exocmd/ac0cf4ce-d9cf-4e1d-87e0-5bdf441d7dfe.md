---
exo__Asset_uid: ac0cf4ce-d9cf-4e1d-87e0-5bdf441d7dfe
exo__Asset_createdAt: 2026-08-28T21:48:35
exo__Asset_updatedAt: 2026-08-28T21:48:35
exo__Instance_class:
  - "[[11579feb-2e42-491c-af59-b89b1129a539]]"
exo__Asset_createdBy: "[[4ef3962d-b8a7-42b5-bd28-88ec846f1d13]]"
exo__Asset_label: Append value to exo__Instance_class (additive)
aliases:
  - Append value to exo__Instance_class (additive)
exo__Asset_isDefinedBy: "[[60967c6a-4e8a-4ee3-8922-db98b981e4f4]]"
exocmd__Grounding_type: "[[572f7e69-a8a1-42f6-8113-5aa65cc4b552]]"
exocmd__Grounding_targetProperty: exo__Instance_class
exocmd__Grounding_appendExpression: $input.class
---

Основание типа `property_append` для **аддитивного** дописывания класса в
`exo__Instance_class`.

## Зачем отдельное основание

`exo__Instance_class` **guarded** в CLI: `set-property` отвечает fail-loud
«has a dedicated guarded command … Use: exocortex apply convert-to-task|convert-to-project».
Гвард верен — реклассинг есть семантическая операция с предусловием. Но обе названные
команды **ЗАМЕНЯЮТ** класс, а конвейеру нужно **дописать** второй, сохранив первый:
аддитивная миграция `18857d67` сознательно оставила `ems__*` рядом с `flow__*`
(правило `additive-migration-creates-two-state-models`), и снятие исходного класса
отменило бы её решение.

`property_append` — ровно эта операция: добавить элемент в multi-value список, не тронув
существующие. Гвард на неё не распространяется: он живёт в command-слое CLI
(`set-property` / `remove-property`, 3 call-site функции `guardedRouteFor`), а
`GroundingExecutor` его не консультирует.

Проверено **исполнением** 2026-08-28 на одноразовом ассете (тикет `e7acd416`):
`ems__Task` → после apply список содержит И `ems__Task`, И `flow__Task`, rc=0.

## Форма

- `exocmd__Grounding_targetProperty` = `exo__Instance_class`
- `exocmd__Grounding_appendExpression` = `$input.class` — значение задаёт вызывающий,
  потому что flow-тип выводится из класса-источника и различается по тикетам.

Вызывающий передаёт значение уже в вики-форме: `--input '{"class":"<вики-ссылка на uid>"}'`.

## Кто зовёт

`~/.claude/bin/vteam-record.sh`, функция `create_attempt` — материализует проекцию
`flow__WorkItem_projectsFrom` в момент диспатча, чтобы `flow__Attempt_item` (range
`flow__WorkItem`) был удовлетворён. До этого 13 спавнов подряд отвечали `record-failed rc=6`.

