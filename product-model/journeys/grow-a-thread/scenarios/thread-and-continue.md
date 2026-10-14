---
kind: primary
result: achieved
routes:
  web: Web
steps:
  - text: "The User creates a thread from selected messages"
    kind: actor
    actor: user
    capability: create-thread
    entities:
      - { entity: thread, effect: creates, to: Active, facts: [Name] }
      - { entity: message, as: forward, effect: creates, facts: [Content, Sent at, Forwarded from, Timeline position], with: thread }
    contexts: { web: { place: roomy-app::spaces::channel } }
  - text: "The Product opens the new thread"
    kind: product
    actor: user
    capability: create-thread
    entities:
      - { entity: thread, effect: reads, facts: [Name] }
    contexts: { web: { place: roomy-app::spaces::thread } }
  - text: "The User writes the next message in the thread"
    kind: actor
    actor: user
    capability: send-message
    entities:
      - { entity: message, as: next, effect: creates, facts: [Content, Sent at, Mentions, Timeline position] }
      - { entity: thread, effect: reads, facts: [] }
    contexts: { web: { place: roomy-app::spaces::thread } }
---

# Create a thread and continue in it

## Trigger

A side conversation is crowding a channel.

## Outcome

The conversation continues in its own thread.
