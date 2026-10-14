---
appliesTo:
  - { type: entity, id: federation, effect: changes, facts: [Receiver access] }
permits:
  - related: [{ verb: requests, entity: space }, { verb: has, entity: membership }, { verb: holds, entity: user }]
    when:
      - { entity: membership, fact: Role, is: Admin }
      - { entity: membership, fact: Banned, is: "No" }
references:
  - { kind: code, role: implementation, target: "packages/appserver/src/auth/writeAuth.ts" }
---

# Only the receiving space's admins set access to shared channels

The requesting space's admins decide what their members and roles may do in a shared channel, never more than the origin shares; a channel the origin does not share cannot be given any access.
