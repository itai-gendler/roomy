---
kind: primary
routes:
  web: Web
steps:
  - text: "The User confirms archiving the thread"
    kind: actor
    actor: user
    entities:
      - { entity: thread, effect: changes, from: Active, to: Archived, facts: [] }
    contexts: { web: { place: roomy-app::spaces::thread-settings } }
---

# Archive a thread

## Trigger

A thread has run its course.

## Outcome

Only admins still see it.
