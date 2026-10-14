---
kind: primary
routes:
  web: Web
steps:
  - text: "The User chooses a handle, an email and a password"
    kind: actor
    actor: user
    entities:
      - { entity: user, effect: creates, facts: [Handle] }
    contexts: { web: { place: roomy-app::welcome::register } }
  - text: "The Product creates the account and returns to sign-in with the new handle filled in"
    kind: product
    actor: user
    entities:
      - { entity: user, effect: reads, facts: [Handle] }
    contexts: { web: { place: roomy-app::welcome::sign-in } }
---

# Register with a handle

## Trigger

Somebody without an AT Protocol account wants to use Roomy.

## Outcome

The account exists and the sign-in form is ready with its handle.

## Edge cases

- The account server refuses a handle already taken, and the reason is shown.
