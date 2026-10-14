---
entities:
  - { entity: space, shows: [Name] }
  - { entity: federation, shows: [Request message, Requested at], collects: [Request message, Shared channels] }
  - { entity: channel, shows: [Name] }
entryPoints:
  - roomy-app: "/{space}/settings/federations"
references:
  - { kind: code, role: implementation, target: "packages/app-lite/src/routes/[space]/settings/federations/+page.svelte" }
---

# Federation

A space's federation requests and the channels it shares with other spaces.
