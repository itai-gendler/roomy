---
kind: primary
routes:
  web: Web
steps:
  - text: "The User renames the category and saves the sidebar"
    kind: actor
    actor: user
    entities:
      - { entity: category, effect: changes, facts: [Name] }
    contexts: { web: { place: roomy-app::spaces::category-settings } }
---

# Rename a category

## Trigger

A category's name no longer fits.

## Outcome

The category carries the new name once the sidebar is saved.
