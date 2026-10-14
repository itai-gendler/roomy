---
kind: primary
routes:
  web: Web
steps:
  - text: "The User confirms archiving the channel"
    kind: actor
    actor: user
    entities:
      - { entity: channel, effect: changes, from: Active, to: Archived, facts: [] }
    contexts: { web: { place: roomy-app::spaces::channel-settings } }
---

# Archive a channel

## Trigger

A channel has gone quiet for good.

## Outcome

Only admins still see it.
