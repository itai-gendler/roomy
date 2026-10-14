---
kind: alternative
routes:
  web: Web
steps:
  - text: "The User attaches images to a message and sends it"
    kind: actor
    actor: user
    entities:
      - { entity: message, effect: creates, facts: [Content, Sent at, Media, Timeline position] }
    contexts: { web: { place: roomy-app::spaces::channel } }
---

# Send a message with images

## Trigger

The user wants to share pictures in a public space.

## Outcome

The message carries the uploaded media.

## Edge cases

- Attaching media is not offered in invite-only spaces.
