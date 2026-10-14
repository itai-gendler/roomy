---
appliesTo:
  - { type: entity, id: role, effect: removes }
permits:
  - related: [{ verb: defines, entity: space }, { verb: has, entity: membership }, { verb: holds, entity: user }]
    when:
      - { entity: membership, fact: Role, is: Admin }
      - { entity: membership, fact: Banned, is: "No" }
references:
  - { kind: code, role: implementation, target: "packages/appserver/src/auth/writeAuth.ts#checkWriteAuth" }
---

# Only admins delete roles

Deleting a role takes away the access it gave.
