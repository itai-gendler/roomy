---
kind: primary
routes:
  web: Web
steps:
  - text: "The User enables notifications and allows them on the device"
    kind: actor
    actor: user
    entities:
      - { entity: push-subscription, effect: creates, facts: [Device, Registered at] }
    contexts: { web: { place: roomy-app::spaces::notification-settings } }
---

# Turn on notifications

## Trigger

The user wants to hear about mentions while away.

## Outcome

This device receives notifications.

## Edge cases

- If the device refuses permission, notifications stay off and the page says so.
