---
entities:
  - { entity: space, shows: [Name, Join policy] }
  - { entity: membership, collects: [Update rhythm] }
  - { entity: invite, shows: [Link] }
entryPoints:
  - roomy-app: "/join"
references:
  - { kind: code, role: implementation, target: "packages/app-lite/src/routes/join/[[spaceRef]]/+page.svelte" }
  - { kind: code, role: implementation, target: "packages/app-lite/src/lib/components/layout/JoinSpaceModal.svelte" }
---

# Join space

Where a person who followed a space or invite link sees the space and joins it.
