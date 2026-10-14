---
appliesTo:
  - { type: entity, id: membership, effect: changes, facts: [Banned] }
permits:
  - related: [{ verb: has, entity: space }, { verb: has, entity: membership }, { verb: holds, entity: user }]
    when:
      - { entity: membership, fact: Role, is: Admin }
      - { entity: membership, fact: Banned, is: "No" }
references:
  - { kind: code, role: implementation, target: "packages/appserver/src/auth/writeAuth.ts#checkWriteAuth" }
---

# Only admins ban and unban

Banning shuts a user out of reading, writing and rejoining the space.
