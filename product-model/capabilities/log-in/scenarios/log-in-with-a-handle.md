---
kind: primary
routes:
  web: Web
steps:
  - text: "The User enters their handle"
    kind: actor
    actor: user
    entities:
      - { entity: user, effect: reads, facts: [Handle] }
    contexts: { web: { place: roomy-app::welcome::sign-in } }
  - text: "The User approves Roomy at their own account server"
    kind: actor
    actor: user
    entities: []
    contexts: { web: { place: roomy-app::welcome::sign-in } }
  - text: "The Product signs them in and opens Home"
    kind: product
    actor: user
    entities:
      - { entity: user, effect: reads, facts: [Display name, Avatar] }
    contexts: { web: { place: roomy-app::welcome::sign-in } }
---

# Log in with a handle

## Trigger

A person opens Roomy while signed out.

## Outcome

They are signed in and see their spaces.

## Edge cases

- Picking the account signed in with last time skips typing the handle.
