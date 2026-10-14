---
availability:
  - { place: roomy-app::spaces }
references:
  - { kind: code, role: implementation, target: "packages/app-lite/src/routes/new/+page.svelte" }
  - { kind: code, role: implementation, target: "packages/appserver/src/handlers/space.roomy.space.createSpace.ts#createSpaceHandler" }
  - { kind: code, role: implementation, target: "packages/sdk/src/operations/space.ts#createDefaultSpaceEvents" }
---

# Create space

Start a new space with a name, description and picture, choosing whether anyone may join, whether members may invite, and whether it may be suggested to others. The creator becomes its first admin and the space starts with a lobby channel in a general category.
