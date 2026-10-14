---
availability:
  - { place: roomy-app::spaces }
domain: sidebar
references:
  - { kind: code, role: implementation, target: "packages/app-lite/src/lib/components/ui/ChannelPermissions.svelte" }
  - { kind: code, role: implementation, target: "packages/sdk/src/schema/events/roles.ts#SetRoleRoomPermission" }
---

# Change role access

An admin gives a role None, Read, or Read & Write in a channel whose members have less than Read & Write.
