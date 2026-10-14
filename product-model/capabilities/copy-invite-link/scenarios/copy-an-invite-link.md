---
kind: alternative
routes:
  web: Web
steps:
  - text: "The User copies an invite link from the list"
    kind: actor
    actor: user
    entities:
      - { entity: invite, effect: reads, facts: [Link] }
    contexts: { web: { place: roomy-app::spaces::invites } }
---

# Copy an invite link

## Trigger

The user wants to share an existing invite link.

## Outcome

The invite link is on the clipboard.
