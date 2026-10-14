---
kind: primary
routes:
  web: Web
steps:
  - text: "The User edits their name, description, pronouns, website, picture or banner and saves"
    kind: actor
    actor: user
    entities:
      - { entity: user, effect: changes, facts: [Display name, Description, Pronouns, Website, Avatar, Banner] }
    contexts: { web: { place: roomy-app::spaces::profile } }
  - text: "The Product keeps the profile in the user's own account"
    kind: product
    actor: user
    entities:
      - { entity: user, effect: reads, facts: [] }
    contexts: { web: { place: roomy-app::spaces::profile } }
---

# Edit one's own profile

## Trigger

The user wants people in their spaces to know more about them.

## Outcome

Their profile shows the new details wherever they appear.
