---
kind: primary
routes:
  web: Web
steps:
  - text: "The User picks an archived channel and restores it"
    kind: actor
    actor: user
    entities:
      - { entity: channel, effect: changes, from: Archived, to: Active, facts: [] }
    contexts: { web: { place: roomy-app::spaces::archive } }
---

# Restore an archived channel

## Trigger

An archived channel is needed again.

## Outcome

The channel is back for everyone who may read it.

## Edge cases

- With nothing archived, the archive says there is nothing to restore.
