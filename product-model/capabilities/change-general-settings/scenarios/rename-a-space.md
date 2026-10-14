---
kind: alternative
routes:
  web: Web
steps:
  - text: "The User changes the name, description or picture and saves"
    kind: actor
    actor: user
    entities:
      - { entity: space, effect: changes, facts: [Name, Description, Avatar] }
    contexts: { web: { place: roomy-app::spaces::general-settings } }
---

# Rename a space

## Trigger

The community has a new name or picture.

## Outcome

The space shows the new name, description and picture everywhere.

## Edge cases

- Choosing whether the space may be suggested to others is saved the same way.
