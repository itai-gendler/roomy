---
availability:
  - { place: roomy-app::spaces }
domain: sidebar
references:
  - { kind: code, role: implementation, target: "packages/app-lite/src/lib/components/sidebar/SpaceSidebar.svelte" }
  - { kind: code, role: implementation, target: "packages/app-lite/src/lib/mutations/room.ts#createRoom" }
---

# Create channel

An admin adds a channel to a space, open to all members or limited to roles.
