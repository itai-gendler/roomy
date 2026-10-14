---
kind: alternative
routes:
  web: Web
steps:
  - text: "The User selects several messages and chooses Delete"
    kind: actor
    actor: user
    entities:
      - { entity: message, effect: reads, facts: [Content] }
    contexts: { web: { place: roomy-app::spaces::channel } }
  - text: "The User confirms deleting messages other people wrote"
    kind: actor
    actor: user
    entities:
      - { entity: message, effect: removes }
    contexts: { web: { place: roomy-app::spaces::channel } }
  - text: "The Product reports how many messages were deleted and leaves selection"
    kind: product
    actor: user
    entities:
      - { entity: message, effect: reads, facts: [] }
    contexts: { web: { place: roomy-app::spaces::channel } }
---

# Admin deletes selected messages

## Trigger

An admin cleans up a run of messages by several people.

## Outcome

The selected messages are gone and the admin is told how many.
