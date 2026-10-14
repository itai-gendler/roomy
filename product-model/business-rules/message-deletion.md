---
appliesTo:
  - { type: entity, id: message, effect: removes }
permits:
  - related: [{ verb: sends, entity: user }]
  - related: [{ verb: contains, entity: channel }, { verb: contains, entity: space }, { verb: has, entity: membership }, { verb: holds, entity: user }]
    when:
      - { entity: membership, fact: Role, is: Admin }
      - { entity: membership, fact: Banned, is: "No" }
  - related: [{ verb: contains, entity: thread }, { verb: has, entity: channel }, { verb: contains, entity: space }, { verb: has, entity: membership }, { verb: holds, entity: user }]
    when:
      - { entity: membership, fact: Role, is: Admin }
      - { entity: membership, fact: Banned, is: "No" }
references:
  - { kind: code, role: implementation, target: "packages/appserver/src/auth/writeAuth.ts#checkWriteAuth" }
---

# Authors and admins delete messages

A message is deleted by its author or by an admin of the space.
