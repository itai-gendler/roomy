---
kind: primary
routes:
  web: Web
steps:
  - text: "The User renames the thread and saves"
    kind: actor
    actor: user
    entities:
      - { entity: thread, effect: changes, facts: [Name] }
    contexts: { web: { place: roomy-app::spaces::thread-settings } }
---

# Rename a thread

## Trigger

A thread's name no longer says what it is about.

## Outcome

Everyone sees the new name.
