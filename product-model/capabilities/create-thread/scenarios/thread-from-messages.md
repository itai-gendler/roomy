---
kind: primary
routes:
  web: Web
steps:
  - text: "The User chooses Create Thread on a message and selects any further messages"
    kind: actor
    actor: user
    entities:
      - { entity: message, as: original, effect: reads, facts: [Content] }
      - { entity: thread, effect: reads, facts: [] }
    contexts: { web: { place: roomy-app::spaces::channel } }
  - text: "The User names the thread and creates it"
    kind: actor
    actor: user
    entities:
      - { entity: thread, effect: creates, to: Active, facts: [Name] }
      - { entity: message, as: forward, effect: creates, facts: [Content, Sent at, Forwarded from, Timeline position], with: thread }
    contexts: { web: { place: roomy-app::spaces::channel } }
  - text: "The Product opens the new thread"
    kind: product
    actor: user
    entities:
      - { entity: thread, effect: reads, facts: [Name] }
    contexts: { web: { place: roomy-app::spaces::thread } }
---

# Create a thread from messages

## Trigger

A side conversation in a channel deserves its own room.

## Outcome

A named thread holds the chosen messages and the user is in it.
