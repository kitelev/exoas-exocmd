---
exo__Asset_uid: 8d44243f-73af-44ff-b9ca-d7e4bfa6aa3d
exo__Asset_createdAt: 2026-08-03T18:16:18
exo__Asset_updatedAt: 2026-08-03T18:16:18
exo__Instance_class:
  - "[[81c5d3c0-e2f2-4f7d-a19d-de91f414340e]]"
exo__Asset_createdBy: "[[4ef3962d-b8a7-42b5-bd28-88ec846f1d13]]"
exo__Asset_label: exocmd__Grounding_incrementBy
aliases:
  - exocmd__Grounding_incrementBy
exo__Asset_isDefinedBy: "[[60967c6a-4e8a-4ee3-8922-db98b981e4f4]]"
exo__Property_domain: "[[11579feb-2e42-491c-af59-b89b1129a539]]"
exo__Property_description: Шаг приращения для основания, увеличивающего числовое свойство. Range xsd:decimal. Cardinality 0..1.
exo__Property_displayName: incrementBy
---

# exocmd__Grounding_incrementBy

`exo__NumberProperty` на `exocmd__Grounding` (cardinality 0..1, range `xsd:decimal`).

Величина приращения для основания, увеличивающего числовое свойство ассета.

Разбирается загрузчиком в число — нечисловое значение отвергается на разборе, а не на исполнении.

## Замер на момент объявления

Носителей в живом графе (vault-my, 2026-08-03) — **1**. Объявлено в рамках `ems__Bug` `63e438c2`: загрузчик читал 30 полей основания, объявлено было 22.

