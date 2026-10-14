---
availability:
  - { place: roomy-app::spaces }
domain: sidebar
references:
  - { kind: code, role: implementation, target: "packages/app-lite/src/lib/components/sidebar/EditRoomModal.svelte" }
  - { kind: code, role: implementation, target: "packages/design/src/components/ui/PermissionEditor.svelte" }
---

# Edit channel

An admin renames a channel and sets what every member may do in it — None, Read, or Read & Write. For a channel another space shares in, the admin sets what their own members may do there instead.
