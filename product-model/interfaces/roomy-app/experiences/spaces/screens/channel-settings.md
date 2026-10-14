---
entities:
  - { entity: channel, collects: [Name, Members access] }
  - { entity: federation, collects: [Receiver access] }
  - { entity: role, shows: [Name] }
  - { entity: space, shows: [Name] }
  - { entity: channel-permission, collects: [Access] }
references:
  - { kind: code, role: implementation, target: "packages/app-lite/src/lib/components/sidebar/EditRoomModal.svelte" }
  - { kind: code, role: implementation, target: "packages/app-lite/src/lib/components/ui/ChannelPermissions.svelte" }
---

# Channel settings

Where an admin renames a channel, sets who may read and write it, or archives it.
