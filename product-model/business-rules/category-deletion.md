---
appliesTo:
  - { type: entity, id: category, effect: removes }
permits:
  - related: [{ verb: contains, entity: space }, { verb: has, entity: membership }, { verb: holds, entity: user }]
    when:
      - { entity: membership, fact: Role, is: Admin }
      - { entity: membership, fact: Banned, is: "No" }
references:
  - { kind: code, role: implementation, target: "packages/appserver/src/auth/writeAuth.ts#checkWriteAuth" }
---

# Only admins delete categories

A deleted category's channels stay in the space, uncategorized.
