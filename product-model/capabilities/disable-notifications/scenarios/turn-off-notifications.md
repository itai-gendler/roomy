---
kind: primary
routes:
  web: Web
steps:
  - text: "The User disables notifications"
    kind: actor
    actor: user
    entities:
      - { entity: push-subscription, effect: removes }
    contexts: { web: { place: roomy-app::spaces::notification-settings } }
---

# Turn off notifications

## Trigger

The user no longer wants notifications on this device.

## Outcome

This device stops receiving notifications.
