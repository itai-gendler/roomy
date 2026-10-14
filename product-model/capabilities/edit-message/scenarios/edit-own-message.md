---
kind: primary
routes:
  web: Web
steps:
  - text: "The User chooses Edit on their message, changes the text and saves"
    kind: actor
    actor: user
    entities:
      - { entity: message, effect: changes, facts: [Content, Mentions, Link previews, Edited] }
    contexts: { web: { place: roomy-app::spaces::channel } }
---

# Edit one's own message

## Trigger

The author spots a mistake in their message.

## Outcome

The message shows the new text and that it was edited.

## Edge cases

- Escape cancels the edit and leaves the message unchanged.
- A forward has no Edit, since its content is the original's.
