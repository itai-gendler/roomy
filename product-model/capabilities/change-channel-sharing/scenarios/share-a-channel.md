---
kind: primary
routes:
  web: Web
steps:
  - text: "The User sets a channel to Read or Read + write for the federated space"
    kind: actor
    actor: user
    entities:
      - { entity: channel, effect: reads, facts: [Name] }
      - { entity: federation, effect: changes, facts: [Shared channels] }
      - { entity: space, effect: reads, facts: [] }
    contexts: { web: { place: roomy-app::spaces::federation-settings } }
---

# Share a channel

## Trigger

The admins want the federated space to join a channel's conversation.

## Outcome

The channel appears in the federated space at the chosen level.

## Edge cases

- Setting a channel to Off stops sharing it.
