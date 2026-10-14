---
kind: primary
routes:
  web: Web
steps:
  - text: "The User drags categories and channels into a new arrangement and saves"
    kind: actor
    actor: user
    entities:
      - { entity: space, effect: changes, facts: [Category order] }
      - { entity: category, effect: changes, facts: [Channels] }
      - { entity: channel, effect: reads, facts: [] }
    contexts: { web: { place: roomy-app::spaces::space-sidebar } }
---

# Rearrange the sidebar

## Trigger

The space has grown and its sidebar needs order.

## Outcome

Everyone sees categories and channels in the new arrangement.

## Edge cases

- Cancelling leaves the sidebar as it was.
- A failed save keeps the editing session open with an error.
