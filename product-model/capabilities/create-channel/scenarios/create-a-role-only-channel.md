---
kind: alternative
routes:
  web: Web
steps:
  - text: "The User names a new channel, lowers what members may do, and gives chosen roles access"
    kind: actor
    actor: user
    entities:
      - { entity: channel, effect: creates, to: Active, facts: [Name, Members access] }
      - { entity: channel-permission, effect: creates, facts: [Access], with: channel }
      - { entity: role, effect: reads, facts: [] }
    contexts: { web: { place: roomy-app::spaces::space-sidebar } }
  - text: "The Product opens the new channel"
    kind: product
    actor: user
    entities:
      - { entity: channel, effect: reads, facts: [Name] }
    contexts: { web: { place: roomy-app::spaces::channel } }
---

# Create a channel for some roles

## Trigger

A channel is meant for some roles only.

## Outcome

Only admins and the chosen roles may read or write it.
