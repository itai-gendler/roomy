---
kind: primary
routes:
  web: Web
steps:
  - text: "The User writes a message, mentioning members if they like, and sends it"
    kind: actor
    actor: user
    entities:
      - { entity: message, effect: creates, facts: [Content, Sent at, Mentions, Timeline position] }
    contexts: { web: { place: roomy-app::spaces::channel } }
  - text: "The Product adds previews of the message's links"
    kind: product
    actor: user
    entities:
      - { entity: message, effect: changes, facts: [Link previews] }
    contexts: { web: { place: roomy-app::spaces::channel } }
---

# Send a message in a channel

## Trigger

The user has something to say in a channel.

## Outcome

The message appears for everyone who may read the channel, with previews of its links.

## Edge cases

- A message that cannot be delivered stays in the timeline marked Not sent, to retry or discard.
