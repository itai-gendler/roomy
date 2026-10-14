---
kind: primary
routes:
  web: Web
steps:
  - text: "The User opens Home"
    kind: actor
    actor: user
    entities:
      - { entity: space, effect: reads, facts: [Name] }
      - { entity: channel, effect: reads, facts: [Name] }
      - { entity: thread, effect: reads, facts: [Name] }
      - { entity: message, effect: reads, facts: [Content, Sent at] }
    contexts: { web: { place: roomy-app::spaces::home } }
---

# See recent activity

## Trigger

The user opens Roomy to catch up.

## Outcome

They see the rooms with the newest messages they may read, and can open one.
