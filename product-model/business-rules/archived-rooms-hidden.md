---
appliesTo:
  - { type: entity, id: channel, effect: changes, to: Archived }
  - { type: entity, id: thread, effect: changes, to: Archived }
references:
  - { kind: code, role: implementation, target: "packages/appserver/src/handlers/space.roomy.space.getMetadata.ts" }
---

# Archived channels and threads are seen only by admins

Archiving never deletes a room; it hides it from everyone but the space's admins.
