---
kind: alternative
routes:
  web: Web
steps:
  - text: "The User lowers what members may do in the channel to Read or None and saves"
    kind: actor
    actor: user
    entities:
      - { entity: channel, effect: changes, facts: [Members access] }
    contexts: { web: { place: roomy-app::spaces::channel-settings } }
---

# Restrict what members may do

## Trigger

A channel should be read-only for ordinary members, or hidden from them.

## Outcome

Members without a role may only read the channel, or no longer see it.
