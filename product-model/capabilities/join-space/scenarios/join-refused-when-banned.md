---
kind: validation
routes:
  web: Web
steps:
  - text: "The User tries to join the space"
    kind: actor
    actor: user
    entities:
      - { entity: space, effect: reads, facts: [Name] }
    contexts: { web: { place: roomy-app::spaces::join } }
  - text: "The User is banned from the space"
    kind: condition
    actor: user
    entities:
      - { entity: membership, effect: reads, facts: [Banned] }
      - { entity: space, effect: reads, facts: [] }
      - { entity: user, effect: reads, facts: [] }
    contexts: { web: { place: roomy-app::spaces::join } }
  - text: "The Product refuses and says they are banned from the space"
    kind: product
    actor: user
    entities:
      - { entity: space, effect: reads, facts: [] }
    contexts: { web: { place: roomy-app::spaces::join } }
---

# Join refused when banned

## Trigger

A banned user follows the space's link again.

## Outcome

They stay out and are told they are banned.
