---
kind: primary
routes:
  web: Web
steps:
  - text: "The User finds a member by name and adds them to the role"
    kind: actor
    actor: user
    entities:
      - { entity: user, effect: reads, facts: [Display name, Handle] }
      - { entity: role, effect: changes, facts: [Members] }
    contexts: { web: { place: roomy-app::spaces::permissions-settings } }
---

# Give a member a role

## Trigger

A member should get a role's access.

## Outcome

The member holds the role.
