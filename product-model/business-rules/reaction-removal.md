---
appliesTo:
  - { type: entity, id: reaction, effect: removes }
permits:
  - related: [{ verb: adds, entity: user }]
references:
  - { kind: code, role: implementation, target: "packages/app-lite/src/lib/components/chat/MessageReactions.svelte" }
---

# Only the reactor takes a reaction back

A reaction belongs to the user who added it.
