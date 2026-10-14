---
domain: sidebar
relations:
  - { entity: channel, verb: groups, cardinality: one-to-many }
references:
  - { kind: code, role: implementation, target: "packages/sdk/src/schema/events/space.ts#UpdateSidebar" }
---

# Category

A named group of channels in a space's sidebar.

## Information kept

- **Name** — the category's name
- **Channels** — the channels in the category, in their sidebar order
