---
appliesTo:
  - { type: entity, id: membership, effect: changes, facts: [Update rhythm] }
permits:
  - related: [{ verb: holds, entity: user }]
references:
  - { kind: code, role: implementation, target: "packages/appserver/src/handlers/space.roomy.push.setPreferences.ts" }
---

# Only the member sets their update rhythm for a space

How much a space notifies someone is their own choice.
