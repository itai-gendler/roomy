---
kind: primary
routes:
  web: Web
steps:
  - text: "A new message mentions a member or replies to one of their messages"
    kind: condition
    unattended: true
    entities:
      - { entity: message, effect: reads, facts: [Mentions, Reply to] }
    contexts: { web: { place: roomy-app::spaces } }
  - text: "The member may read the room and has notifications on"
    kind: condition
    entities:
      - { entity: membership, effect: reads, facts: [Update rhythm] }
      - { entity: push-subscription, effect: reads, facts: [Device] }
    contexts: { web: { place: roomy-app::spaces } }
  - text: "The Product notifies the member's devices with the message"
    kind: product
    entities:
      - { entity: message, effect: reads, facts: [Content] }
    contexts: { web: { place: roomy-app::spaces } }
---

# Notify a mentioned member

## Trigger

Someone mentions a member, or replies to their message.

## Outcome

The member's devices show the message, unless their rhythm is Silent.
