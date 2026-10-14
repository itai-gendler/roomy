---
appliesTo:
  - { type: entity, id: message, effect: changes, facts: [Timeline position] }
permits:
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

# Only admins move messages

Moving rewrites another room's timeline, so it is curation the admins do, and only within their own space.
