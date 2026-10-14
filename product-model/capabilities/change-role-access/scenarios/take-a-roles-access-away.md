---
kind: alternative
routes:
  web: Web
steps:
  - text: "The User sets a role to None and saves"
    kind: actor
    actor: user
    entities:
      - { entity: channel-permission, effect: removes }
      - { entity: role, effect: reads, facts: [] }
    contexts: { web: { place: roomy-app::spaces::channel-settings } }
---

# Take a role's access away

## Trigger

A role should no longer reach the channel.

## Outcome

The role's members lose the access the role gave them.
