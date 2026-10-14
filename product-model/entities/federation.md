---
domain: federation
references:
  - { kind: code, role: implementation, target: "packages/sdk/src/schema/events/federation.ts" }
  - { kind: code, role: implementation, target: "packages/appserver/src/auth/federation.ts" }
  - { kind: doc, role: context, target: "packages/appserver/docs/plans/channel-federation.md" }
---

# Federation

An agreement between two spaces through which one space, the origin, shares some of its channels into another, the requesting space, whose members then read and write there.

## Information kept

- **Request message** — the note the requesting space's admin sent with the request
- **Requested at** — when the request was sent
- **Shared channels** — the origin's channels shared through it, each at Read or Read + write
- **Receiver access** — for each shared channel, what the requesting space's members and roles may do there, never more than the origin shares

## States

### Pending

The request awaits the origin space's admins.

### Active

The origin approved it; shared channels appear in the requesting space.

### Rejected

The origin turned the request down.

### Removed

An admin of either space ended it; every shared channel stops being shared.
