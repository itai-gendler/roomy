---
domain: invites
references:
  - { kind: code, role: implementation, target: "packages/sdk/src/schema/events/invite.ts" }
  - { kind: code, role: implementation, target: "packages/appserver/src/handlers/space.roomy.space.getInvites.ts" }
---

# Invite

A link that lets people join an invite-only space.

## Information kept

- **Link** — the address that carries the invite
- **Created at** — when it was created
