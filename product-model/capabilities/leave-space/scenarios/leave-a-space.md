---
kind: primary
routes:
  web: Web
steps:
  - text: "The User chooses to leave the space"
    kind: actor
    actor: user
    entities:
      - { entity: membership, effect: changes, from: Joined, to: Left, facts: [] }
      - { entity: space, effect: reads, facts: [] }
    contexts: { web: { place: roomy-app::spaces::general-settings } }
  - text: "The Product takes the User Home"
    kind: product
    actor: user
    entities:
      - { entity: user, effect: reads, facts: [] }
    contexts: { web: { place: roomy-app::spaces::home } }
---

# Leave a space

## Trigger

The user no longer wants to be part of a space.

## Outcome

The space leaves their list and appears under their left spaces; they return Home.
