---
kind: alternative
routes:
  web: Web
steps:
  - text: "The User opens the space index"
    kind: actor
    actor: user
    entities:
      - { entity: thread, effect: reads, facts: [Name] }
      - { entity: channel, effect: reads, facts: [Name] }
      - { entity: message, effect: reads, facts: [Content, Sent at] }
      - { entity: read-position, effect: reads, facts: [Unread count] }
      - { entity: space, effect: reads, facts: [] }
    contexts: { web: { place: roomy-app::spaces::space-index } }
---

# Browse a space's threads

## Trigger

The user opens a space without picking a channel.

## Outcome

They see the space's threads and channels by latest activity.
