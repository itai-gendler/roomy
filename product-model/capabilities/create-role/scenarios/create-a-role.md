---
kind: primary
routes:
  web: Web
steps:
  - text: "The User names and describes a new role"
    kind: actor
    actor: user
    entities:
      - { entity: role, effect: creates, facts: [Name, Description, Members] }
    contexts: { web: { place: roomy-app::spaces::permissions-settings } }
---

# Create a role

## Trigger

The space needs a group of members with shared access, such as moderators.

## Outcome

The role is listed and can be given to members and channels.
