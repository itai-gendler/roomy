---
kind: primary
routes:
  web: Web
steps:
  - text: "The User gives a role Read or Read & Write in the channel and saves"
    kind: actor
    actor: user
    entities:
      - { entity: role, effect: reads, facts: [Name] }
      - { entity: channel-permission, effect: creates, facts: [Access] }
      - { entity: channel, effect: reads, facts: [] }
    contexts: { web: { place: roomy-app::spaces::channel-settings } }
---

# Give a role access to a channel

## Trigger

A restricted channel is meant for one role.

## Outcome

Members holding the role may read, or read and write, the channel.
