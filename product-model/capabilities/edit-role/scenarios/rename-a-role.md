---
kind: primary
routes:
  web: Web
steps:
  - text: "The User edits the role's name or description and saves"
    kind: actor
    actor: user
    entities:
      - { entity: role, effect: changes, facts: [Name, Description] }
    contexts: { web: { place: roomy-app::spaces::permissions-settings } }
---

# Rename a role

## Trigger

A role's name or purpose changed.

## Outcome

The role carries the new name and description.
