---
appliesTo:
  - { type: entity, id: category, effect: changes }
permits:
  - related: [{ verb: contains, entity: space }, { verb: has, entity: membership }, { verb: holds, entity: user }]
    when:
      - { entity: membership, fact: Role, is: Admin }
      - { entity: membership, fact: Banned, is: "No" }
references:
  - { kind: code, role: implementation, target: "packages/appserver/src/auth/writeAuth.ts#checkWriteAuth" }
---

# Only admins change categories

Renaming a category or moving channels in it is an admin's job.
