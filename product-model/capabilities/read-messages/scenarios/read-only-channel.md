---
kind: alternative
routes:
  web: Web
steps:
  - text: "The User opens a channel they may only read"
    kind: actor
    actor: user
    entities:
      - { entity: channel, effect: reads, facts: [Name, Members access] }
      - { entity: message, effect: reads, facts: [Content, Sent at, Reply to, Mentions, Media, Link previews, Forwarded from, Edited] }
    contexts: { web: { place: roomy-app::spaces::channel } }
  - text: "The User may not write in the channel"
    kind: condition
    actor: user
    entities:
      - { entity: channel, effect: reads, facts: [Members access] }
      - { entity: user, effect: reads, facts: [] }
    contexts: { web: { place: roomy-app::spaces::channel } }
  - text: "The Product shows a notice in place of the composer"
    kind: product
    actor: user
    entities: []
    contexts: { web: { place: roomy-app::spaces::channel } }
---

# Read a channel one may not write in

## Trigger

The user may read a channel but not write in it.

## Outcome

They read the conversation, and the composer says they cannot post.
