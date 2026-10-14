---
appliesTo:
  - { type: entity, id: membership, effect: creates }
  - { type: capability, id: join-space }
references:
  - { kind: code, role: implementation, target: "packages/sdk/src/schema/events/space.ts#JoinSpace" }
---

# Joining is announced in the first channel

When someone joins, the space's first channel gets a message saying so.
