---
kind: alternative
routes:
  web: Web
steps:
  - text: "The User switches a role between Read and Read & Write and saves"
    kind: actor
    actor: user
    entities:
      - { entity: channel-permission, effect: changes, facts: [Access] }
      - { entity: role, effect: reads, facts: [] }
    contexts: { web: { place: roomy-app::spaces::channel-settings } }
---

# Change a role's level

## Trigger

A role should now be able to write as well as read.

## Outcome

The role's members get the new level.
