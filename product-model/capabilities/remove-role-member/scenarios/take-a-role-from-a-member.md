---
kind: primary
routes:
  web: Web
steps:
  - text: "The User removes a member from the role"
    kind: actor
    actor: user
    entities:
      - { entity: role, effect: changes, facts: [Members] }
    contexts: { web: { place: roomy-app::spaces::permissions-settings } }
---

# Take a role from a member

## Trigger

A member should no longer hold a role.

## Outcome

The member loses the role and the access it gave.
