---
kind: primary
routes:
  web: Web
steps:
  - text: "The User opens Members and searches by name"
    kind: actor
    actor: user
    entities:
      - { entity: membership, effect: reads, facts: [Role, Banned] }
      - { entity: user, effect: reads, facts: [Display name, Handle] }
    contexts: { web: { place: roomy-app::spaces::members-settings } }
---

# See a space's members

## Trigger

The user wants to know who is in the space.

## Outcome

They see the members matching their search, marked admin or banned.
