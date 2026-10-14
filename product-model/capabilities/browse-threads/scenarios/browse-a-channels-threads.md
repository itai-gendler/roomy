---
kind: primary
routes:
  web: Web
steps:
  - text: "The User opens the channel's Threads tab"
    kind: actor
    actor: user
    entities:
      - { entity: thread, effect: reads, facts: [Name] }
      - { entity: message, effect: reads, facts: [Content, Sent at] }
      - { entity: read-position, effect: reads, facts: [Unread count] }
      - { entity: channel, effect: reads, facts: [] }
    contexts: { web: { place: roomy-app::spaces::channel } }
---

# Browse a channel's threads

## Trigger

The user wants to see what grew out of a channel.

## Outcome

They see the channel's threads by latest activity and can open one.

## Edge cases

- A channel without threads says there are none yet.
