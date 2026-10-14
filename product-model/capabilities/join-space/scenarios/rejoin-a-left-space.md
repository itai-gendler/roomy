---
kind: alternative
routes:
  web: Web
steps:
  - text: "The User chooses Rejoin on a space under their left spaces"
    kind: actor
    actor: user
    entities:
      - { entity: space, effect: reads, facts: [Name] }
      - { entity: membership, effect: changes, from: Left, to: Joined, facts: [Joined at] }
    contexts: { web: { place: roomy-app::spaces::account-settings } }
---

# Rejoin a space one left

## Trigger

The user wants back into a space they left.

## Outcome

They are a member again, with the role they held before.
