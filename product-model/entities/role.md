---
domain: permissions
relations:
  - { entity: channel-permission, verb: has, cardinality: one-to-many }
references:
  - { kind: code, role: implementation, target: "packages/sdk/src/schema/events/roles.ts" }
  - { kind: code, role: implementation, target: "packages/appserver/src/handlers/space.roomy.space.getRoles.ts" }
---

# Role

A named group of members that an admin creates in a space and gives access to channels.

## Information kept

- **Name** — the role's name
- **Description** — what the role is for
- **Members** — the members who hold the role
