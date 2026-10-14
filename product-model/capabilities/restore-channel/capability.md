---
availability:
  - { place: roomy-app::spaces }
domain: sidebar
references:
  - { kind: code, role: implementation, target: "packages/app-lite/src/lib/components/sidebar/RestoreRoomModal.svelte" }
  - { kind: code, role: implementation, target: "packages/sdk/src/schema/events/room.ts#RestoreRoom" }
---

# Restore channel

An admin brings an archived channel back.
