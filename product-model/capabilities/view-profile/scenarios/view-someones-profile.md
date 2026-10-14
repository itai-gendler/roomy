---
kind: primary
routes:
  web: Web
steps:
  - text: "The User opens a person's profile from their message"
    kind: actor
    actor: user
    entities:
      - { entity: user, effect: reads, facts: [Display name, Handle, Avatar, Banner, Description, Pronouns, Website] }
      - { entity: message, effect: reads, facts: [] }
    contexts: { web: { place: roomy-app::spaces::profile } }
---

# View someone's profile

## Trigger

The user wonders who wrote a message.

## Outcome

They see that person's profile.
