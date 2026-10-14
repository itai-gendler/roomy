---
appliesTo:
  - { type: entity, id: membership, effect: changes, facts: [Role] }
permits:
  - related: [{ verb: has, entity: space }, { verb: has, entity: membership }, { verb: holds, entity: user }]
    when:
      - { entity: membership, fact: Role, is: Admin }
      - { entity: membership, fact: Banned, is: "No" }
references:
  - { kind: code, role: implementation, target: "packages/appserver/src/auth/writeAuth.ts#checkWriteAuth" }
---

# Only admins promote and demote admins

Admin status is granted and withdrawn by admins.
