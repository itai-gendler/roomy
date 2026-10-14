---
kind: primary
result: achieved
routes:
  web: Web
steps:
  - text: "The User creates a space with a name"
    kind: actor
    actor: user
    capability: create-space
    entities:
      - { entity: space, effect: creates, facts: [Name, Description, Avatar, Join policy, Member invites, Suggested to others, Category order] }
      - { entity: membership, effect: creates, to: Joined, facts: [Role, Banned, Joined at], with: space }
      - { entity: category, effect: creates, facts: [Name, Channels], with: space }
      - { entity: channel, effect: creates, to: Active, facts: [Name, Members access], with: category }
    contexts: { web: { place: roomy-app::spaces::new-space } }
  - text: "The Product makes the User its first admin and opens the space"
    kind: product
    actor: user
    capability: create-space
    entities:
      - { entity: membership, effect: reads, facts: [Role] }
      - { entity: space, effect: reads, facts: [] }
      - { entity: user, effect: reads, facts: [] }
    contexts: { web: { place: roomy-app::spaces::space-index } }
  - text: "The User sees the space's channels and threads by activity"
    kind: actor
    actor: user
    capability: browse-threads
    entities:
      - { entity: channel, effect: reads, facts: [Name] }
      - { entity: space, effect: reads, facts: [] }
      - { entity: thread, effect: reads, facts: [] }
    contexts: { web: { place: roomy-app::spaces::space-index } }
---

# Create a space and land in it

## Trigger

The user wants a home for their community.

## Outcome

They are inside the new space.
