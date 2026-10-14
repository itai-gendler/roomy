---
kind: primary
routes:
  web: Web
steps:
  - text: "The User chooses Unban Member"
    kind: actor
    actor: user
    entities:
      - { entity: membership, effect: changes, facts: [Banned] }
    contexts: { web: { place: roomy-app::spaces::members-settings } }
---

# Unban a member

## Trigger

A banned member is welcome again.

## Outcome

The member reads and writes in the space as before.
