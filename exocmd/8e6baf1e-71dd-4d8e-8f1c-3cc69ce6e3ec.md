---
exo__Asset_uid: 8e6baf1e-71dd-4d8e-8f1c-3cc69ce6e3ec
exo__Asset_label: Relocate to source ontology folder
exo__Asset_isDefinedBy: "[[60967c6a-4e8a-4ee3-8922-db98b981e4f4]]"
exo__Asset_createdAt: 2026-07-13T00:00:08+0500
exo__Instance_class:
  - "[[11579feb-2e42-491c-af59-b89b1129a539]]"
exocmd__Grounding_type: "[[9bf9fc99-ac37-4e51-b9f5-bd920099947c]]"
exocmd__Grounding_targetProperty: repairFolder
---

# Relocate to source ontology folder

Step 2 of the «Un-archive Ontologically» composite — the inverse of the forward
step 2 ([[08da54cf-a587-4cf2-a144-ea195fd6cf66|Relocate to archive ontology folder]]).
A `service_call` grounding dispatching the registered `repairFolder` service
(serviceId carried in `exocmd__Grounding_targetProperty`). After step 1 re-anchored
`exo__Asset_isDefinedBy` back to the source ontology, `repairFolder` reads the
(now restored) `isDefinedBy`, resolves the source ontology's folder and physically
relocates the asset there — the co-location invariant. Runs **after** step 1 so
it sees the restored `isDefinedBy`.
