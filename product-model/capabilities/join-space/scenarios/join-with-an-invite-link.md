---
kind: alternative
routes:
  web: Web
steps:
  - text: "The User opens the invite link"
    kind: actor
    actor: user
    entities:
      - { entity: space, effect: reads, facts: [Name, Join policy] }
      - { entity: invite, effect: reads, facts: [] }
    contexts: { web: { place: roomy-app::spaces::join } }
  - text: "The User picks an update rhythm and joins"
    kind: actor
    actor: user
    entities:
      - { entity: membership, effect: creates, to: Joined, facts: [Role, Banned, Joined at, Update rhythm] }
    contexts: { web: { place: roomy-app::spaces::join } }
  - text: "The Product announces in the space's first channel that the User joined"
    kind: product
    actor: user
    entities:
      - { entity: message, effect: creates, facts: [Content, Sent at] }
      - { entity: channel, effect: reads, facts: [] }
      - { entity: space, effect: reads, facts: [] }
      - { entity: user, effect: reads, facts: [] }
    contexts: { web: { place: roomy-app::spaces::join } }
---

# Join with an invite link

## Trigger

Someone shared an invite link to an invite-only space.

## Outcome

The user is a member of the invite-only space.
