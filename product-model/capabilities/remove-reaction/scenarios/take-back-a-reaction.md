---
kind: primary
routes:
  web: Web
steps:
  - text: "The User chooses their own reaction on a message"
    kind: actor
    actor: user
    entities:
      - { entity: reaction, effect: removes }
      - { entity: message, effect: reads, facts: [] }
    contexts: { web: { place: roomy-app::spaces::channel } }
---

# Take back a reaction

## Trigger

The user reacted by mistake.

## Outcome

Their reaction is gone.
