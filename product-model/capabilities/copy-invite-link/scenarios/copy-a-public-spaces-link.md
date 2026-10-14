---
kind: primary
routes:
  web: Web
steps:
  - text: "The User asks to share a public space"
    kind: actor
    actor: user
    entities:
      - { entity: space, effect: reads, facts: [Name, Join policy] }
    contexts: { web: { place: roomy-app::spaces::space-sidebar } }
  - text: "The Product copies the space's link and confirms it was copied"
    kind: product
    actor: user
    entities:
      - { entity: space, effect: reads, facts: [] }
    contexts: { web: { place: roomy-app::spaces::space-sidebar } }
---

# Copy a public space's link

## Trigger

The user wants to bring a friend into a public space.

## Outcome

The space's link is on the clipboard.
