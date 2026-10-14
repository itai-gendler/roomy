---
kind: edge
routes:
  web: Web
steps:
  - text: "The User enters their handle"
    kind: actor
    actor: user
    entities:
      - { entity: user, effect: reads, facts: [Handle] }
    contexts: { web: { place: roomy-app::welcome::sign-in } }
  - text: "The account server does not answer or refuses for now"
    kind: condition
    actor: user
    entities: []
    contexts: { web: { place: roomy-app::welcome::sign-in } }
  - text: "The Product explains that their account server could not be reached and keeps them signed out"
    kind: product
    actor: user
    entities: []
    contexts: { web: { place: roomy-app::welcome::sign-in } }
---

# Account server unavailable

## Trigger

The person's account server is unreachable or rate-limits the attempt.

## Outcome

They stay signed out with an explanation and can try again.
