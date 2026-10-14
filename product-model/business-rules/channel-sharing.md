---
appliesTo:
  - { type: entity, id: federation, effect: changes, facts: [Shared channels] }
permits:
  - related: [{ verb: receives, entity: space }, { verb: has, entity: membership }, { verb: holds, entity: user }]
    when:
      - { entity: membership, fact: Role, is: Admin }
      - { entity: membership, fact: Banned, is: "No" }
references:
  - { kind: code, role: implementation, target: "packages/appserver/src/auth/writeAuth.ts#checkWriteAuth" }
---

# Only the origin's admins choose what is shared

Which channels a federation shares, and at which level, is set by the origin space's admins.
