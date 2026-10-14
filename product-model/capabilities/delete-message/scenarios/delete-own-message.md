---
kind: primary
routes:
  web: Web
steps:
  - text: "The User chooses Delete on their message and confirms"
    kind: actor
    actor: user
    entities:
      - { entity: message, effect: removes }
    contexts: { web: { place: roomy-app::spaces::channel } }
---

# Delete one's own message

## Trigger

The author regrets a message.

## Outcome

The message is gone for everyone.

## Edge cases

- Cancelling the confirmation leaves the message and the room as they were.
