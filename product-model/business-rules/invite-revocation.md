---
appliesTo:
  - { type: entity, id: invite, effect: removes }
permits:
  - related: [{ verb: has, entity: space }, { verb: has, entity: membership }, { verb: holds, entity: user }]
    when:
      - { entity: membership, fact: Role, is: Admin }
      - { entity: membership, fact: Banned, is: "No" }
references:
  - { kind: code, role: implementation, target: "packages/appserver/src/auth/writeAuth.ts#checkWriteAuth" }
---

# Only admins revoke invite links

Revoking a link stops it admitting anyone.
