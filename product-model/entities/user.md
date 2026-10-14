---
kind: person
acts: external
relations:
  - { entity: membership, verb: holds, cardinality: one-to-many }
  - { entity: message, verb: sends, cardinality: one-to-many }
  - { entity: reaction, verb: adds, cardinality: one-to-many }
  - { entity: invite, verb: creates, cardinality: one-to-many }
  - { entity: role, verb: holds, cardinality: many-to-many }
  - { entity: push-subscription, verb: registers, cardinality: one-to-many }
  - { entity: read-position, verb: has, cardinality: one-to-many }
references:
  - { kind: code, role: implementation, target: "packages/app-lite/src/lib/auth.svelte.ts" }
  - { kind: code, role: implementation, target: "packages/app-lite/src/routes/user/[user]/+page.svelte" }
  - { kind: code, role: implementation, target: "packages/appserver/src/handlers/space.roomy.user.getProfile.ts" }
---

# User

A person who signs in to Roomy with their AT Protocol account — a Bluesky handle or any other Atmosphere account. Their profile and identity live in their own account; in each space they are in they hold a membership.

## Information kept

- **Handle** — the AT Protocol handle they sign in with
- **Display name** — the name shown beside their messages, from their Roomy profile or else their Bluesky profile
- **Avatar** — their profile picture
- **Banner** — the wide image at the top of their profile
- **Description** — the short text about themselves on their profile
- **Pronouns** — the pronouns shown on their profile
- **Website** — the link shown on their profile
- **Default update rhythm** — how much Roomy notifies them in spaces where they have not chosen otherwise: Silent, Quiet, Engaged or Busy; Engaged until they choose
- **Space order** — the order of their spaces in the space list
