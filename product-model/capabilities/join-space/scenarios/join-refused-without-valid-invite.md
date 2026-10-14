---
kind: validation
routes:
  web: Web
steps:
  - text: "The User tries to join an invite-only space"
    kind: actor
    actor: user
    entities:
      - { entity: space, effect: reads, facts: [Name, Join policy] }
      - { entity: invite, effect: reads, facts: [] }
    contexts: { web: { place: roomy-app::spaces::join } }
  - text: "The link carries no invite, or its invite was revoked"
    kind: condition
    actor: user
    entities:
      - { entity: invite, effect: reads, facts: [] }
    contexts: { web: { place: roomy-app::spaces::join } }
  - text: "The Product refuses and says an invite link is needed"
    kind: product
    actor: user
    entities:
      - { entity: invite, effect: reads, facts: [] }
    contexts: { web: { place: roomy-app::spaces::join } }
---

# Join refused without a valid invite

## Trigger

The user opens a link to an invite-only space without an invite, or with one that was revoked.

## Outcome

They are not a member and are told they need a valid invite link.
