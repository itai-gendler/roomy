---
kind: primary
routes:
  web: Web
steps:
  - text: "The User opens a channel"
    kind: actor
    actor: user
    entities:
      - { entity: channel, effect: reads, facts: [Name] }
      - { entity: message, effect: reads, facts: [Content, Sent at, Reply to, Mentions, Media, Link previews, Forwarded from, Edited] }
      - { entity: reaction, effect: reads, facts: [Emoji] }
    contexts: { web: { place: roomy-app::spaces::channel } }
  - text: "The Product marks the channel read up to the newest message"
    kind: product
    actor: user
    entities:
      - { entity: read-position, effect: changes, facts: [Last read, Unread count] }
      - { entity: channel, effect: reads, facts: [] }
      - { entity: message, effect: reads, facts: [] }
    contexts: { web: { place: roomy-app::spaces::channel } }
---

# Read a channel

## Trigger

The user opens a channel with unread messages.

## Outcome

They see the conversation and the channel no longer counts as unread.
