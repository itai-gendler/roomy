---
appliesTo:
  - { type: entity, id: channel-permission }
  - { type: entity, id: channel, facts: [Members access] }
references:
  - { kind: code, role: implementation, target: "packages/design/src/components/ui/PermissionEditor.svelte" }
---

# Role access matters only while members have less than Read & Write

While a channel's Members access is Read & Write, every member already reads and writes it, so its role access cannot be managed until an admin lowers it.
