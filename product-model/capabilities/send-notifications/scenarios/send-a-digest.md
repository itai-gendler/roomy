---
kind: alternative
routes:
  web: Web
steps:
  - text: "Unseen messages gather in a room the member has written in"
    kind: condition
    unattended: true
    entities:
      - { entity: message, effect: reads, facts: [Sent at] }
    contexts: { web: { place: roomy-app::spaces } }
  - text: "Five messages arrived or an hour passed"
    kind: condition
    entities:
      - { entity: read-position, effect: reads, facts: [Last read] }
      - { entity: message, effect: reads, facts: [] }
    contexts: { web: { place: roomy-app::spaces } }
  - text: "The Product sends one digest notification for the room"
    kind: product
    entities:
      - { entity: push-subscription, effect: reads, facts: [Device] }
    contexts: { web: { place: roomy-app::spaces } }
---

# Send a digest of a quiet room

## Trigger

Messages pile up in a room an Engaged member has written in.

## Outcome

The member gets one digest notification for that room until they open it.

## Edge cases

- Opening the room starts the count again.
