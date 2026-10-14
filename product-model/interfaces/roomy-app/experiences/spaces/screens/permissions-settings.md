---
entities:
  - { entity: role, collects: [Name, Description, Members] }
  - { entity: user, shows: [Display name, Handle] }
entryPoints:
  - roomy-app: "/{space}/settings/permissions"
references:
  - { kind: code, role: implementation, target: "packages/app-lite/src/routes/[space]/settings/permissions/+page.svelte" }
---

# Permissions

A space's roles and who holds them.
