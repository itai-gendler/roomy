---
kind: primary
routes:
  web: Web
steps:
  - text: "The User names the space, describes it, chooses its join policy and creates it"
    kind: actor
    actor: user
    entities:
      - { entity: space, effect: creates, facts: [Name, Description, Avatar, Join policy, Member invites, Suggested to others, Category order] }
      - { entity: membership, effect: creates, to: Joined, facts: [Role, Banned, Joined at], with: space }
      - { entity: category, effect: creates, facts: [Name, Channels], with: space }
      - { entity: channel, effect: creates, to: Active, facts: [Name, Members access], with: category }
    contexts: { web: { place: roomy-app::spaces::new-space } }
  - text: "The Product makes the User the space's first admin with a lobby channel in a general category"
    kind: product
    actor: user
    entities:
      - { entity: membership, effect: reads, facts: [Role] }
      - { entity: category, effect: reads, facts: [] }
      - { entity: channel, effect: reads, facts: [] }
      - { entity: space, effect: reads, facts: [] }
      - { entity: user, effect: reads, facts: [] }
    contexts: { web: { place: roomy-app::spaces::new-space } }
  - text: "The Product opens the new space"
    kind: product
    actor: user
    entities:
      - { entity: space, effect: reads, facts: [Name] }
    contexts: { web: { place: roomy-app::spaces::space-index } }
---

# Create a public space

## Trigger

The user wants a home for their community.

## Outcome

The space exists with its creator as admin, a general category and a lobby channel.

## Edge cases

- Without a name the space is not created.
- A picture is uploaded before the space is created; a failed upload leaves no space.
