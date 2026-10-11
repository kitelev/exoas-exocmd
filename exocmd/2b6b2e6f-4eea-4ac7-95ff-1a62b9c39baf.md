---
exo__Asset_uid: 2b6b2e6f-4eea-4ac7-95ff-1a62b9c39baf
exo__Asset_createdAt: 2026-10-11T12:39:55
exo__Asset_updatedAt: 2026-10-11T12:39:55
exo__Instance_class:
  - "[[790e5b16-251d-4556-96ac-e5c7f1429b2e]]"
exo__Asset_createdBy: "[[4ef3962d-b8a7-42b5-bd28-88ec846f1d13]]"
exo__Asset_label: Idea — Park
aliases:
  - Idea — Park
exo__Asset_isDefinedBy: "[[60967c6a-4e8a-4ee3-8922-db98b981e4f4]]"
exocmd__Command_icon: pause-circle
exocmd__Command_precondition: "[[5e7a7b9b-1a01-4514-98ed-3db04c986148]]"
exocmd__Command_grounding: "[[6edc82cf-8387-4052-bdeb-020588b055f7]]"
exocmd__Command_successMessage: Idea status set to Отложена
exocmd__Command_category: status
exocmd__Command_cliName: idea-park
exocmd__Command_destructive: true
---

# Idea — Park

Ставит `idea__Idea_status` = «Отложена» у идеи, чей статус — свой (`idea__Idea_status`, тонкая онтология `$idea`), а не `ems__Effort_status`.

## Зачем отдельная команда, а не привязка `park-waiting`

`park-waiting` пишет `ems__Effort_status`, а у `idea__Idea` статус — `idea__Idea_status` (RFC §2a, ✅ решение №8: «кнопки меняют тот статус, что есть у идеи»). Привязать `park-waiting` к `idea__Idea` значило бы писать в идею чужое свойство (нарушение `domain`). Поэтому:
- идея с `ems__Effort_status` (`ems__Idea`) → `park-waiting` (привязка к `ems__Idea`);
- идея без него (`idea__Idea`, `exoization-ideas__ExoizationIdea`, `flow__Idea` и `ems__Idea` без статуса — через мосты) → эта команда.

Предусловие разводит их: на одной идее видна ровно одна пара.

- **Precondition**: `5e7a7b9b`
- **Grounding**: `6edc82cf` (composite)
- **Привязки**: `idea__Idea`, `ems__Idea`, `flow__Idea`. ⛔ Привязки к `ems__Idea` / `flow__Idea` — обход долга Q3 RFC: видимость кнопок читает `exo__Class_superClass` из frontmatter класса и рёбер мостов (`exo__Statement`) не видит; членство в `idea__Idea` проверяет предусловие путём через SPARQL. Когда видимость научится утверждениям — эти две привязки снимаются.
- **Потребитель**: обработчик кнопок недельного дайджеста PO (`~/dotfiles/scripts/po_digest_callback.py`) выбирает команду по свойству статуса элемента.

Источник: RFC `14217015-963b-4020-b267-fd13b1275b3a` §2a/§8, задача P0.4 `61e8ddaa-6c10-4e4a-a3b3-c210a15a012c`

