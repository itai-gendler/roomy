---
kind: primary
routes:
  web: Web
steps:
  - text: "The User chooses Move on a message and picks the destination room"
    kind: actor
    actor: user
    entities:
      - { entity: message, effect: changes, facts: [Timeline position] }
      - { entity: channel, effect: reads, facts: [Name] }
    contexts: { web: { place: roomy-app::spaces::channel } }
---

# Move a message

## Trigger

A message was posted in the wrong channel.

## Outcome

The message now sits in the destination room and no longer in the first.

## Edge cases

- A destination in another space is refused.
