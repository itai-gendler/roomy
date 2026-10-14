---
kind: primary
routes:
  web: Web
steps:
  - text: "The User names a new channel open to every member"
    kind: actor
    actor: user
    entities:
      - { entity: channel, effect: creates, to: Active, facts: [Name, Members access] }
    contexts: { web: { place: roomy-app::spaces::space-sidebar } }
  - text: "The Product opens the new channel"
    kind: product
    actor: user
    entities:
      - { entity: channel, effect: reads, facts: [Name] }
    contexts: { web: { place: roomy-app::spaces::channel } }
---

# Create an open channel

## Trigger

The admins want a new place to talk.

## Outcome

The channel exists and the admin is in it.
