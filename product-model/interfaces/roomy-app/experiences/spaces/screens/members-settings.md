---
entities:
  - { entity: membership, shows: [Role, Banned] }
  - { entity: user, shows: [Display name, Handle] }
entryPoints:
  - roomy-app: "/{space}/settings/members"
references:
  - { kind: code, role: implementation, target: "packages/app-lite/src/routes/[space]/settings/members/+page.svelte" }
---

# Members

A space's members with their admin and ban status.
