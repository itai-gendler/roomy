---
availability:
  - { place: roomy-app::spaces }
domain: general
references:
  - { kind: code, role: implementation, target: "packages/app-lite/src/routes/[space]/settings/+page.svelte" }
  - { kind: code, role: implementation, target: "packages/appserver/src/handlers/space.roomy.space.leaveSpace.ts" }
---

# Leave space

Stop being a member of a space. It moves to the user's left spaces.
