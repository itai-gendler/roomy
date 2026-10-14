---
kind: primary
routes:
  web: Web
steps:
  - text: "The User removes a link preview from their message"
    kind: actor
    actor: user
    entities:
      - { entity: message, effect: changes, facts: [Link previews] }
    contexts: { web: { place: roomy-app::spaces::channel } }
---

# Hide a link preview

## Trigger

A link preview in the author's message is noise.

## Outcome

The link stays; its preview is gone.
