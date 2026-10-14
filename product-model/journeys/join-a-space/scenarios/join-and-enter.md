---
kind: primary
result: achieved
routes:
  web: Web
steps:
  - text: "The User picks an update rhythm and joins"
    kind: actor
    actor: user
    capability: join-space
    entities:
      - { entity: membership, effect: creates, to: Joined, facts: [Role, Banned, Joined at, Update rhythm] }
    contexts: { web: { place: roomy-app::spaces::join } }
  - text: "The Product opens the space"
    kind: product
    actor: user
    capability: join-space
    entities:
      - { entity: space, effect: reads, facts: [Name] }
    contexts: { web: { place: roomy-app::spaces::space-index } }
  - text: "The User sees what is active in the space"
    kind: actor
    actor: user
    capability: browse-threads
    entities:
      - { entity: thread, effect: reads, facts: [Name] }
      - { entity: space, effect: reads, facts: [] }
    contexts: { web: { place: roomy-app::spaces::space-index } }
---

# Join through a link and land in the space

## Trigger

Someone shared a link to a space.

## Outcome

They are inside the space as a member.
