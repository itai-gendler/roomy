---
kind: primary
routes:
  web: Web
steps:
  - text: "The User names a new category"
    kind: actor
    actor: user
    entities:
      - { entity: category, effect: creates, facts: [Name, Channels] }
      - { entity: space, effect: changes, facts: [Category order] }
    contexts: { web: { place: roomy-app::spaces::space-sidebar } }
---

# Add a category

## Trigger

The sidebar needs a new group of channels.

## Outcome

An empty category appears last in the sidebar.
