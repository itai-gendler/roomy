---
kind: primary
routes:
  web: Web
steps:
  - text: "The User chooses Forward on a message"
    kind: actor
    actor: user
    entities:
      - { entity: message, as: original, effect: reads, facts: [Content] }
    contexts: { web: { place: roomy-app::spaces::channel } }
  - text: "The User picks a room they may write in, adds a note if they like, and forwards"
    kind: actor
    actor: user
    entities:
      - { entity: message, as: forward, effect: creates, facts: [Content, Sent at, Forwarded from, Timeline position] }
      - { entity: channel, effect: reads, facts: [Name] }
    contexts: { web: { place: roomy-app::spaces::channel } }
---

# Forward a message

## Trigger

A message belongs in another conversation too.

## Outcome

The destination shows the forward with the original's author, time and content.

## Edge cases

- Only rooms the user may write in are offered.
