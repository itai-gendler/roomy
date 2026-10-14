---
kind: primary
routes:
  web: Web
steps:
  - text: "The User restricts the join policy so joining needs a link, chooses whether ordinary members may hand such links out, and saves"
    kind: actor
    actor: user
    entities:
      - { entity: space, effect: changes, facts: [Join policy, Member invites] }
    contexts: { web: { place: roomy-app::spaces::general-settings } }
---

# Make a space invite-only

## Trigger

The admins want to control who joins.

## Outcome

Joining now needs an invite link, and members may or may not create one as chosen.
