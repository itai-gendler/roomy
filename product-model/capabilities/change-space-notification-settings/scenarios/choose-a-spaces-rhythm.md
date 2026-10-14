---
kind: primary
routes:
  web: Web
steps:
  - text: "The User picks an update rhythm for the space"
    kind: actor
    actor: user
    entities:
      - { entity: membership, effect: changes, facts: [Update rhythm] }
      - { entity: space, effect: reads, facts: [] }
    contexts: { web: { place: roomy-app::spaces::space-notification-settings } }
---

# Choose a space's update rhythm

## Trigger

One space deserves closer attention than the rest.

## Outcome

That space notifies at its own rhythm.
