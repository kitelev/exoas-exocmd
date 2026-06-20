# exoas-exocmd — Exocortex command ontology AssetSpace

**The homoiconic UI-command layer for [Exocortex](https://github.com/kitelev/exocortex).** This repository is an **AssetSpace** — a git-backed package of vault assets you mount into an Exocortex vault. It holds the `exocmd` namespace: the classes that let **commands and the buttons that trigger them be described as data**, plus the actual command/grounding definitions the engine renders.

> **Where this fits.** Exocortex is *homoiconic*: user-configurable behaviour lives in the RDF graph, not hardcoded TypeScript. The buttons you see on an asset's layout — *Create Task*, *Set Status Doing*, *Mark Done*, *Repair Folder* — are not coded into the plugin; they are `exocmd__Command` assets in this AssetSpace. `exoas-exocmd` is a **floor** AssetSpace (mounted alongside `exoas-exo`), because the command machinery is part of the standard experience. See the engine's [Exo-as-SDK topology](https://github.com/kitelev/exocortex/blob/main/docs/explanation/assetspace-sdk-topology.md).

---

## What's in here

A single namespace folder, `exocmd/`, holding the command meta-classes **and** the concrete command/grounding/precondition assets that drive the live UI.

### Core classes

| Class | Role |
| --- | --- |
| `exocmd__Command` | A command — what the button/palette entry *is* (label, cliName, the grounding it runs, its precondition). |
| `exocmd__CommandBinding` | Binds a command to a class/context so it shows up on the right assets. |
| `exocmd__Grounding` | The executable "recipe" of a command — what it actually does (set a property, create an asset, repair a folder, run a service call, …). |
| `exocmd__GroundingType` | The kind of a grounding (`property_set`, `create_instance`, `service_call`, `composite`, …). |
| `exocmd__Precondition` | A guard deciding whether a command is visible/runnable (SPARQL ASK or a registered host function). |
| `exocmd__InheritanceRule` | A rule that copies/derives frontmatter onto a newly created asset (e.g. set `ems__Effort_area` on a child). |
| `exocmd__PropertyDefault` | A default value applied to a property on creation. |
| `exocmd__SubstitutionToken` / `exocmd__SubstitutionTokenLegacy` / `exocmd__TokenInvocation` | The `$token` substitution machinery used inside groundings (e.g. `$isDefinedByFolder`, `$targetClassSelf`). |
| `exocmd__DeclarativeRule` | A declarative behaviour rule. |
| `exocmd__UniversalDefaultTemplate` | A reusable default template. |

### Command definitions (instances)

Most of the assets here are **instances**: the real `exocmd__Command` / `exocmd__Grounding` / `exocmd__Precondition` definitions that produce the engine's stock buttons (create efforts, drive the EMS status lifecycle, repair folders, and more). Editing or adding these is how you change the UI without touching the plugin.

> Every class above is a live asset on disk in `exocmd/`. This README is reference prose; the authoritative definitions are the assets themselves.

---

## Using this AssetSpace

You don't clone this repo into your vault by hand — it is mounted through Exocortex, and as a floor AssetSpace it travels with the standard bootstrap / profile flow:

- **CLI:** `npx @kitelev/exocortex-cli assetspace-add --vault ~/vault --url https://github.com/kitelev/exoas-exocmd` (or it is pulled in as a dependency when you apply a Profile).
- **Plugin:** command palette → **Exocortex: Add a knowledge pack**, or apply a Profile that includes it (`Exocortex: Apply profile`).

Once mounted, its namespace appears under `assetspaces/kitelev/exoas-exocmd/exocmd/`, and the commands render as buttons on matching assets in Reading Mode.

## Conventions (for contributors)

- **UID-canon.** Every asset is a UUID-named file (`<exo__Asset_uid>.md`); the human label lives in `exo__Asset_label`. Wikilinks between assets are by UID.
- **Vault↔code parity.** A precondition that names an `exocmd__Precondition_hostFunction` requires that function to be registered in the engine — an unregistered host function fails *open* on inline buttons. Keep declarations and registrations in sync.
- **CI.** Pushes run the shared [AssetSpace SHACL gate](https://github.com/kitelev/exoas-ci) (`validate schema --shapes-mode`).

## See also

- [Exocortex engine repo](https://github.com/kitelev/exocortex) — the plugin + CLI that execute these commands.
- [exoas-exo](https://github.com/kitelev/exoas-exo) — the core ontology (`exo__Asset`, `exo__Class`, …) this builds on.
- [exoas-public](https://github.com/kitelev/exoas-public) — domain vocabularies; its `ems-commands` / `period-commands` namespaces add domain-specific commands on top of this layer.
- [Exo-as-SDK topology](https://github.com/kitelev/exocortex/blob/main/docs/explanation/assetspace-sdk-topology.md).

## License

MIT — see the [engine repo](https://github.com/kitelev/exocortex/blob/main/LICENSE).
