---
kind: primary
routes:
  web: Web
steps:
  - text: "The User removes the federation and confirms"
    kind: actor
    actor: user
    entities:
      - { entity: federation, effect: changes, from: Active, to: Removed, facts: [] }
    contexts: { web: { place: roomy-app::spaces::federation-settings } }
---

# End a federation

## Trigger

The spaces no longer want to share channels.

## Outcome

The federation is removed and its channels disappear from the other space.

## Edge cases

- The asking space may send a new request after a removal.
