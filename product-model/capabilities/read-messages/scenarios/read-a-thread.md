---
kind: alternative
routes:
  web: Web
steps:
  - text: "The User opens a thread"
    kind: actor
    actor: user
    entities:
      - { entity: thread, effect: reads, facts: [Name] }
      - { entity: message, effect: reads, facts: [Content, Sent at, Reply to, Mentions, Media, Link previews, Forwarded from, Edited] }
    contexts: { web: { place: roomy-app::spaces::thread } }
  - text: "The Product marks the thread read up to the newest message"
    kind: product
    actor: user
    entities:
      - { entity: read-position, effect: changes, facts: [Last read, Unread count] }
      - { entity: message, effect: reads, facts: [] }
      - { entity: thread, effect: reads, facts: [] }
    contexts: { web: { place: roomy-app::spaces::thread } }
---

# Read a thread

## Trigger

The user opens a thread from its channel or the space index.

## Outcome

They see the thread's conversation and it no longer counts as unread.
