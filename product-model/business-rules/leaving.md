---
appliesTo:
  - { type: entity, id: membership, effect: changes, to: Left }
permits:
  - related: [{ verb: holds, entity: user }]
references:
  - { kind: code, role: implementation, target: "packages/appserver/src/handlers/space.roomy.space.leaveSpace.ts" }
---

# Only the member leaves

Leaving a space is the member's own decision.
