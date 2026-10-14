---
kind: primary
result: achieved
routes:
  web: Web
steps:
  - text: "The User creates a channel"
    kind: actor
    actor: user
    capability: create-channel
    entities:
      - { entity: channel, effect: creates, to: Active, facts: [Name, Members access] }
    contexts: { web: { place: roomy-app::spaces::space-sidebar } }
  - text: "The Product opens the new channel"
    kind: product
    actor: user
    capability: create-channel
    entities:
      - { entity: channel, effect: reads, facts: [Name] }
    contexts: { web: { place: roomy-app::spaces::channel } }
  - text: "The User writes the first message"
    kind: actor
    actor: user
    capability: send-message
    entities:
      - { entity: message, effect: creates, facts: [Content, Sent at, Mentions, Timeline position] }
    contexts: { web: { place: roomy-app::spaces::channel } }
---

# Create a channel and post the first message

## Trigger

The admins want a new place to talk.

## Outcome

The channel exists with a first message.
