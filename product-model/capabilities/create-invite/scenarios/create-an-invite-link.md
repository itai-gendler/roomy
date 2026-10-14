---
kind: primary
routes:
  web: Web
steps:
  - text: "The User creates an invite link"
    kind: actor
    actor: user
    entities:
      - { entity: invite, effect: creates, facts: [Link, Created at] }
    contexts: { web: { place: roomy-app::spaces::invites } }
---

# Create an invite link

## Trigger

Someone should be able to join an invite-only space.

## Outcome

A new link is listed, ready to copy.

## Edge cases

- Admins see every link of the space; members see only the links they made.
