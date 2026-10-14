---
availability:
  - { place: roomy-app::spaces }
domain: members
references:
  - { kind: code, role: implementation, target: "packages/app-lite/src/routes/[space]/settings/members/+page.svelte" }
  - { kind: code, role: implementation, target: "packages/appserver/src/handlers/space.roomy.space.getMembers.ts" }
---

# Browse members

See and search a space's members, which of them are admins and which are banned.
