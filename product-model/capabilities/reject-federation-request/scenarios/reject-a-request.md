---
kind: primary
routes:
  web: Web
steps:
  - text: "The User rejects a pending request"
    kind: actor
    actor: user
    entities:
      - { entity: federation, effect: changes, from: Pending, to: Rejected, facts: [] }
    contexts: { web: { place: roomy-app::spaces::federation-settings } }
---

# Reject a request

## Trigger

The admins do not want to share with the asking space.

## Outcome

The request is rejected and the asking space sees so.
