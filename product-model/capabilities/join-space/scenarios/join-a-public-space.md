---
kind: primary
routes:
  web: Web
steps:
  - text: "The User opens the space's link and sees its name"
    kind: actor
    actor: user
    entities:
      - { entity: space, effect: reads, facts: [Name, Join policy] }
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

# Join a public space

## Trigger

The user follows a link to a public space they are not in.

## Outcome

They are a member, the space is in their list, and its first channel announces them.
