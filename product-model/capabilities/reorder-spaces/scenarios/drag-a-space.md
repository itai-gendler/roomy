---
kind: primary
routes:
  web: Web
steps:
  - text: "The User drags a space to a new place in their list"
    kind: actor
    actor: user
    entities:
      - { entity: user, effect: changes, facts: [Space order] }
      - { entity: space, effect: reads, facts: [Name, Avatar] }
    contexts: { web: { place: roomy-app::spaces::space-list } }
---

# Drag a space into place

## Trigger

The user wants their busiest space first.

## Outcome

Their spaces are listed in the new order on every device.
