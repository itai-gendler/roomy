---
kind: primary
routes:
  web: Web
steps:
  - text: "The User confirms deleting the role"
    kind: actor
    actor: user
    entities:
      - { entity: role, effect: removes }
      - { entity: channel-permission, effect: removes, with: role }
    contexts: { web: { place: roomy-app::spaces::permissions-settings } }
---

# Delete a role

## Trigger

A role is no longer used.

## Outcome

The role is gone and grants no access.
