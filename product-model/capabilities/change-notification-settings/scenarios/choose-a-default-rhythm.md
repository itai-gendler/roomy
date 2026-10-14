---
kind: primary
routes:
  web: Web
steps:
  - text: "The User picks a default update rhythm"
    kind: actor
    actor: user
    entities:
      - { entity: user, effect: changes, facts: [Default update rhythm] }
    contexts: { web: { place: roomy-app::spaces::notification-settings } }
---

# Choose a default update rhythm

## Trigger

The user gets too many notifications.

## Outcome

Spaces without their own rhythm follow the new default.
