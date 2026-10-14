---
kind: primary
routes:
  web: Web
steps:
  - text: "The User chooses Promote to Admin on a member"
    kind: actor
    actor: user
    entities:
      - { entity: membership, effect: changes, facts: [Role] }
    contexts: { web: { place: roomy-app::spaces::members-settings } }
---

# Promote a member

## Trigger

A trusted member should help run the space.

## Outcome

The member is an admin.
