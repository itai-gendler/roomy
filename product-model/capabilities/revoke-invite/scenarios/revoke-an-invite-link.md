---
kind: primary
routes:
  web: Web
steps:
  - text: "The User revokes an invite link"
    kind: actor
    actor: user
    entities:
      - { entity: invite, effect: removes }
    contexts: { web: { place: roomy-app::spaces::invites } }
---

# Revoke an invite link

## Trigger

An invite link was shared too widely.

## Outcome

The link no longer lets anyone join.
