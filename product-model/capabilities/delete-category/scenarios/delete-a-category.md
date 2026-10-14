---
kind: primary
routes:
  web: Web
steps:
  - text: "The User confirms deleting the category and saves the sidebar"
    kind: actor
    actor: user
    entities:
      - { entity: category, effect: removes }
      - { entity: space, effect: changes, facts: [Category order] }
    contexts: { web: { place: roomy-app::spaces::category-settings } }
---

# Delete a category

## Trigger

A category is no longer needed.

## Outcome

The category is gone and its channels sit uncategorized.
