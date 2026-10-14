---
appliesTo:
  - { type: entity, id: channel, effect: changes }
permits:
  - related: [{ verb: contains, entity: space }, { verb: has, entity: membership }, { verb: holds, entity: user }]
    when:
      - { entity: membership, fact: Role, is: Admin }
      - { entity: membership, fact: Banned, is: "No" }
references:
  - { kind: code, role: implementation, target: "packages/appserver/src/auth/writeAuth.ts#checkWriteAuth" }
---

# Only admins change channels

Renaming, setting who may read and write, archiving and restoring a channel are the admins'.
