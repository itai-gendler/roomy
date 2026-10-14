---
relations:
  - { entity: message, verb: contains, cardinality: one-to-many }
  - { entity: thread, verb: has, cardinality: one-to-many }
  - { entity: channel-permission, verb: has, cardinality: one-to-many }
references:
  - { kind: code, role: implementation, target: "packages/sdk/src/schema/events/room.ts" }
  - { kind: code, role: implementation, target: "packages/appserver/src/auth/access.ts#computeRoomAccess" }
---

# Channel

A top-level room of a space where members chat, listed in the sidebar. Its conversations can grow into threads.

## Information kept

- **Name** — the channel's name
- **Members access** — what every member may do in it without a role: None, Read, or Read & Write; Read & Write unless an admin restricts it

## States

### Active

The channel is listed in the sidebar for everyone who may read it.

### Archived

Only admins see the channel; they can restore it from the sidebar.
