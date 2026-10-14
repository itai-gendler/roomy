---
kind: alternative
routes:
  web: Web
steps:
  - text: "The User sets what this space's members and roles may do in the shared channel and saves"
    kind: actor
    actor: user
    entities:
      - { entity: federation, effect: changes, facts: [Receiver access] }
      - { entity: channel, effect: reads, facts: [] }
      - { entity: role, effect: reads, facts: [] }
      - { entity: space, effect: reads, facts: [] }
    contexts: { web: { place: roomy-app::spaces::channel-settings } }
---

# Set access to a shared channel

## Trigger

Another space shares a channel into this one.

## Outcome

This space's members and roles may do what the admin chose there, within what the origin shares.

## Edge cases

- The name of a shared channel cannot be changed from the receiving space.
