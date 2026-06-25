---
exo__Asset_isDefinedBy: "[[60967c6a-4e8a-4ee3-8922-db98b981e4f4]]"
exo__Asset_uid: cd6ef6f6-e6cc-476c-baf4-181fb7a78dee
exo__Asset_createdAt: 2026-06-20T15:10:00
exo__Asset_updatedAt: 2026-06-20T15:10:00
exo__Instance_class:
  - "[[9a1cf31c-9d41-4ef3-9023-584a8d087d16|exo__ObjectProperty]]"
exo__Property_domain: "[[11579feb-2e42-491c-af59-b89b1129a539]]"
exo__Property_range: "[[8bdf4506-80bf-4999-8fda-1ea0808b4ee5|exotemplate__Template]]"
exo__Property_description: "ObjectProperty referencing an exotemplate__Template asset whose markdown BODY is loaded (via the plugin TemplateLoaderPort) and used as the body template for a body_template grounding (subproject 17f58ebe Веха 3). Preferred over inline exocmd__Grounding_bodyTemplate when both are set."
exo__Asset_label: exocmd__Grounding_templateRef
aliases:
  - exocmd__Grounding_templateRef
exo__Property_displayName: templateRef
---

Ссылка на `exotemplate__Template` ассет для grounding-типа `body_template`. Тело шаблона загружается рантаймом и резолвится по `$token`. Альтернатива — inline `exocmd__Grounding_bodyTemplate`.