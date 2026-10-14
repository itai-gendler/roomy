---
availability:
  - { place: roomy-app::spaces }
domain: sidebar
references:
  - { kind: code, role: implementation, target: "packages/app-lite/src/lib/components/sidebar/EditRoomModal.svelte" }
  - { kind: code, role: implementation, target: "packages/sdk/src/schema/events/room.ts#DeleteRoom" }
---

# Archive channel

An admin archives a channel: it disappears for everyone but admins and can be restored.
