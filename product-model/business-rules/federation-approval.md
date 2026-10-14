---
appliesTo:
  - { type: entity, id: federation, effect: changes, to: Active }
permits:
  - related: [{ verb: receives, entity: space }, { verb: has, entity: membership }, { verb: holds, entity: user }]
    when:
      - { entity: membership, fact: Role, is: Admin }
      - { entity: membership, fact: Banned, is: "No" }
references:
  - { kind: code, role: implementation, target: "packages/appserver/src/auth/writeAuth.ts#checkWriteAuth" }
---

# Only the origin's admins approve federation

Sharing a space's channels is its own admins' decision.
