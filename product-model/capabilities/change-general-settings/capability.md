---
availability:
  - { place: roomy-app::spaces }
domain: general
references:
  - { kind: code, role: implementation, target: "packages/app-lite/src/routes/[space]/settings/+page.svelte" }
  - { kind: code, role: implementation, target: "packages/sdk/src/schema/events/space.ts#UpdateSpaceInfo" }
---

# Change general settings

An admin changes a space's name, description, picture, join policy, whether members may invite, and whether the space may be suggested to others.
