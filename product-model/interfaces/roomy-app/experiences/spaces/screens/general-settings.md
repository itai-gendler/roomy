---
entities:
  - { entity: space, collects: [Join policy, Member invites, Name, Description, Avatar] }
entryPoints:
  - roomy-app: "/{space}/settings"
references:
  - { kind: code, role: implementation, target: "packages/app-lite/src/routes/[space]/settings/+page.svelte" }
---

# General settings

A space's name, description, picture and join policy, and leaving the space.
