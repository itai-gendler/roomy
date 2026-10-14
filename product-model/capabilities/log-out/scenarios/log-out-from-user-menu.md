---
kind: primary
routes:
  web: Web
steps:
  - text: "The User chooses Log Out"
    kind: actor
    actor: user
    entities: []
    contexts: { web: { place: roomy-app::spaces } }
  - text: "The Product ends the session"
    kind: product
    actor: user
    entities: []
    contexts: { web: { place: roomy-app::spaces } }
---

# Log out from the user menu

## Trigger

The user is done with Roomy on this device.

## Outcome

The session ends and Roomy asks them to sign in again.
