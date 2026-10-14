---
kind: validation
routes:
  web: Web
steps:
  - text: "The User sends a request to a space"
    kind: actor
    actor: user
    entities:
      - { entity: space, effect: reads, facts: [Name] }
    contexts: { web: { place: roomy-app::spaces::federation-settings } }
  - text: "A federation between the two spaces is already active or was rejected"
    kind: condition
    actor: user
    entities:
      - { entity: federation, effect: reads, facts: [] }
      - { entity: space, effect: reads, facts: [] }
    contexts: { web: { place: roomy-app::spaces::federation-settings } }
  - text: "The Product refuses the request"
    kind: product
    actor: user
    entities: []
    contexts: { web: { place: roomy-app::spaces::federation-settings } }
---

# Request refused for an existing federation

## Trigger

The two spaces already federate, or the origin rejected an earlier request.

## Outcome

No new request is made and the admin is told why.
