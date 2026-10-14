---
availability:
  - { place: roomy-app::spaces }
domain: members
references:
  - { kind: code, role: implementation, target: "packages/sdk/src/schema/events/space.ts#BanAccount" }
---

# Ban member

An admin bans a member, who can then no longer read, write or rejoin in the space.
