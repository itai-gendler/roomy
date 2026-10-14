---
relations:
  - { entity: message, verb: contains, cardinality: one-to-many }
references:
  - { kind: code, role: implementation, target: "packages/app-lite/src/lib/mutations/thread.ts#createThread" }
  - { kind: code, role: implementation, target: "packages/appserver/src/auth/access.ts#resolveRoom" }
---

# Thread

A room that grows out of a channel's conversation, with its own name, messages and unread count, linked to the channel it came from.

## Information kept

- **Name** — the thread's name

## States

### Active

The thread is listed with its channel's threads.

### Archived

Only admins see the thread.
