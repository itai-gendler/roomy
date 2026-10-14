---
kind: primary
routes:
  web: Web
steps:
  - text: "The User reads a pending request"
    kind: actor
    actor: user
    entities:
      - { entity: federation, effect: reads, facts: [Request message, Requested at] }
    contexts: { web: { place: roomy-app::spaces::federation-settings } }
  - text: "The User approves it"
    kind: actor
    actor: user
    entities:
      - { entity: federation, effect: changes, from: Pending, to: Active, facts: [] }
    contexts: { web: { place: roomy-app::spaces::federation-settings } }
---

# Approve a request

## Trigger

Another space asked to share this space's channels.

## Outcome

The federation is active and channels can be shared with that space.
