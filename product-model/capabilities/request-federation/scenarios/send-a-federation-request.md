---
kind: primary
routes:
  web: Web
steps:
  - text: "The User picks a space they are a member of, adds a note for its admins, and sends the request"
    kind: actor
    actor: user
    entities:
      - { entity: space, effect: reads, facts: [Name] }
      - { entity: federation, effect: creates, to: Pending, facts: [Request message, Requested at] }
    contexts: { web: { place: roomy-app::spaces::federation-settings } }
---

# Send a federation request

## Trigger

Two communities want to talk in shared channels.

## Outcome

The request awaits the other space's admins.

## Edge cases

- Spaces that already federate with this one, or turned it down, are not offered.
