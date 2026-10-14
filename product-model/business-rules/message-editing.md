---
appliesTo:
  - { type: entity, id: message, effect: changes, facts: [Content, Mentions, Link previews, Edited] }
permits:
  - related: [{ verb: sends, entity: user }]
references:
  - { kind: code, role: implementation, target: "packages/app-lite/src/lib/components/chat/ChatMessage.svelte" }
---

# Only the author edits a message

A message's words, mentions and previews are its author's. A forward cannot be edited, since its content is the original's.
