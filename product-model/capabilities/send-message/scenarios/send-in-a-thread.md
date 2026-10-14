---
kind: alternative
routes:
  web: Web
steps:
  - text: "The User writes a message in the thread and sends it"
    kind: actor
    actor: user
    entities:
      - { entity: message, effect: creates, facts: [Content, Sent at, Mentions, Timeline position] }
      - { entity: thread, effect: reads, facts: [] }
    contexts: { web: { place: roomy-app::spaces::thread } }
---

# Send a message in a thread

## Trigger

The user continues a conversation in a thread.

## Outcome

The message appears in the thread.
