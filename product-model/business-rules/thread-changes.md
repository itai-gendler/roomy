---
appliesTo:
  - { type: entity, id: thread, effect: changes }
permits:
  - related: [{ verb: has, entity: channel }, { verb: contains, entity: space }, { verb: has, entity: membership }, { verb: holds, entity: user }]
    when:
      - { entity: membership, fact: Role, is: Admin }
      - { entity: membership, fact: Banned, is: "No" }
references:
  - { kind: code, role: implementation, target: "packages/appserver/src/auth/writeAuth.ts#checkWriteAuth" }
---

# Only admins rename or archive threads

A thread's name and whether it is archived are the admins' to change.
