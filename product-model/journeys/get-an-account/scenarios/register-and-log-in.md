---
kind: primary
result: achieved
routes:
  web: Web
steps:
  - text: "The User registers with a handle, email and password"
    kind: actor
    actor: user
    capability: register-account
    entities:
      - { entity: user, effect: creates, facts: [Handle] }
    contexts: { web: { place: roomy-app::welcome::register } }
  - text: "The Product returns to sign-in with the new handle filled in"
    kind: product
    actor: user
    capability: register-account
    entities:
      - { entity: user, effect: reads, facts: [Handle] }
    contexts: { web: { place: roomy-app::welcome::sign-in } }
  - text: "The User logs in with the new handle"
    kind: actor
    actor: user
    capability: log-in
    entities:
      - { entity: user, effect: reads, facts: [Handle] }
    contexts: { web: { place: roomy-app::welcome::sign-in } }
---

# Register and log in

## Trigger

Somebody new wants to use Roomy.

## Outcome

They are signed in.
