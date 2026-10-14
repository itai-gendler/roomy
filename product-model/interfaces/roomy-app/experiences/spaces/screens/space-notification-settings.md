---
entities:
  - { entity: membership, collects: [Update rhythm] }
  - { entity: space, shows: [Name] }
entryPoints:
  - roomy-app: "/{space}/settings/notifications"
references:
  - { kind: code, role: implementation, target: "packages/app-lite/src/routes/[space]/settings/notifications/+page.svelte" }
---

# Space notifications

The update rhythm the user chose for one space.
