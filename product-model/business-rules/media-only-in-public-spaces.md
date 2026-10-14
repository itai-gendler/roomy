---
appliesTo:
  - { type: entity, id: message, effect: creates, facts: [Media] }
  - { type: entity, id: space, facts: [Join policy] }
references:
  - { kind: code, role: implementation, target: "packages/app-lite/src/routes/[space]/[room]/+page.svelte" }
---

# Media can be attached only in public spaces

Attachments are kept where anyone could fetch them, so the composer offers no uploads in invite-only spaces.
