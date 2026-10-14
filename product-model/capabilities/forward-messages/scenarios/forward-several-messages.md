---
kind: alternative
routes:
  web: Web
steps:
  - text: "The User selects several messages and chooses Forward"
    kind: actor
    actor: user
    entities:
      - { entity: message, as: original, effect: reads, facts: [Content] }
    contexts: { web: { place: roomy-app::spaces::channel } }
  - text: "The User picks a destination room and forwards"
    kind: actor
    actor: user
    entities:
      - { entity: message, as: forward, effect: creates, facts: [Content, Sent at, Forwarded from, Timeline position] }
    contexts: { web: { place: roomy-app::spaces::channel } }
---

# Forward several messages

## Trigger

A run of messages belongs elsewhere together.

## Outcome

The forwards land in the destination in their original order.
