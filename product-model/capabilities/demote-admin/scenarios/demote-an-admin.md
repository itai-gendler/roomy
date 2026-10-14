---
kind: primary
routes:
  web: Web
steps:
  - text: "The User chooses Demote Admin on another admin"
    kind: actor
    actor: user
    entities:
      - { entity: membership, effect: changes, facts: [Role] }
    contexts: { web: { place: roomy-app::spaces::members-settings } }
---

# Demote an admin

## Trigger

An admin steps back.

## Outcome

They are an ordinary member.

## Edge cases

- Admins are not offered actions on themselves.
