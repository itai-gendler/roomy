---
kind: edge
routes:
  web: Web
steps:
  - text: "The User sends a message"
    kind: actor
    actor: user
    entities:
      - { entity: message, effect: reads, facts: [] }
    contexts: { web: { place: roomy-app::spaces::channel } }
  - text: "The space is being rebuilt"
    kind: condition
    actor: user
    entities:
      - { entity: space, effect: reads, facts: [] }
    contexts: { web: { place: roomy-app::spaces::channel } }
  - text: "The Product keeps the message waiting to send rather than failing it"
    kind: product
    actor: user
    entities:
      - { entity: message, effect: reads, facts: [] }
    contexts: { web: { place: roomy-app::spaces::channel } }
---

# Send while the space is being rebuilt

## Trigger

The space is briefly being set up again on the server.

## Outcome

The message waits and is sent once the space is ready.
