---
kind: primary
routes:
  web: Web
steps:
  - text: "The User renames the channel and saves"
    kind: actor
    actor: user
    entities:
      - { entity: channel, effect: changes, facts: [Name] }
    contexts: { web: { place: roomy-app::spaces::channel-settings } }
---

# Rename a channel

## Trigger

A channel's name no longer fits.

## Outcome

Everyone sees the new name.
