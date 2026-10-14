---
kind: alternative
routes:
  web: Web
steps:
  - text: "The User chooses Reply on a message"
    kind: actor
    actor: user
    entities:
      - { entity: message, as: original, effect: reads, facts: [Content] }
    contexts: { web: { place: roomy-app::spaces::channel } }
  - text: "The User writes the reply and sends it"
    kind: actor
    actor: user
    entities:
      - { entity: message, as: reply, effect: creates, facts: [Content, Sent at, Reply to, Timeline position] }
    contexts: { web: { place: roomy-app::spaces::channel } }
---

# Reply to a message

## Trigger

The user answers one message in particular.

## Outcome

The reply shows the message it answers.
