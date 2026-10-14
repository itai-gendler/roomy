---
kind: primary
routes:
  web: Web
steps:
  - text: "The User chooses Ban Member and confirms"
    kind: actor
    actor: user
    entities:
      - { entity: membership, effect: changes, facts: [Banned] }
    contexts: { web: { place: roomy-app::spaces::members-settings } }
---

# Ban a member

## Trigger

A member keeps breaking the community's norms.

## Outcome

The member is marked banned and shut out of the space.
