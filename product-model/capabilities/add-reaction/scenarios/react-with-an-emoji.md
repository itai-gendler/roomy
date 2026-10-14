---
kind: primary
routes:
  web: Web
steps:
  - text: "The User picks an emoji on a message"
    kind: actor
    actor: user
    entities:
      - { entity: message, effect: reads, facts: [Content] }
      - { entity: reaction, effect: creates, facts: [Emoji] }
    contexts: { web: { place: roomy-app::spaces::channel } }
---

# React with an emoji

## Trigger

The user wants to acknowledge a message without writing.

## Outcome

The emoji shows on the message with a count, and who reacted is listed on hover.

## Edge cases

- Picking an emoji someone else already used adds the user to it.
