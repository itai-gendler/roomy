---
kind: validation
routes:
  web: Web
steps:
  - text: "The User sends a message"
    kind: actor
    actor: user
    entities:
      - { entity: message, effect: reads, facts: [] }
    contexts: { web: { place: roomy-app::spaces::channel } }
  - text: "The User may no longer write in the channel"
    kind: condition
    actor: user
    entities:
      - { entity: channel, effect: reads, facts: [Members access] }
      - { entity: user, effect: reads, facts: [] }
    contexts: { web: { place: roomy-app::spaces::channel } }
  - text: "The Product refuses the message and shows the no-permission notice in place of the composer"
    kind: product
    actor: user
    entities:
      - { entity: message, effect: reads, facts: [] }
    contexts: { web: { place: roomy-app::spaces::channel } }
---

# Send refused without write access

## Trigger

The user's write access was taken away while they had the channel open.

## Outcome

The message is not sent and the composer says they cannot post there.
