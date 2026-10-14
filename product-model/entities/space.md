---
relations:
  - { entity: membership, verb: has, cardinality: one-to-many }
  - { entity: channel, verb: contains, cardinality: one-to-many }
  - { entity: category, verb: contains, cardinality: one-to-many }
  - { entity: role, verb: defines, cardinality: one-to-many }
  - { entity: invite, verb: has, cardinality: one-to-many }
  - { entity: federation, verb: receives, cardinality: one-to-many }
  - { entity: federation, verb: requests, cardinality: one-to-many }
references:
  - { kind: code, role: implementation, target: "packages/sdk/src/schema/events/space.ts" }
  - { kind: code, role: implementation, target: "packages/appserver/src/handlers/space.roomy.space.getMetadata.ts" }
---

# Space

A community's home in Roomy: its channels and their threads, its members, roles and invite links. Each space is its own AT Protocol identity.

## Information kept

- **Name** — the space's name
- **Description** — what the space is about
- **Avatar** — the space's picture
- **Join policy** — Public, where anyone signed in can join, or Invite only, where joining needs an invite link
- **Member invites** — Allowed or Not allowed: whether members who are not admins may create invite links for an invite-only space
- **Suggested to others** — whether the admins agree to the space being suggested to people who are not in it
- **Category order** — the order of the space's categories in its sidebar
