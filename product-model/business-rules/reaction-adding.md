---
appliesTo:
  - { type: entity, id: reaction, effect: creates }
permits:
  - related: [{ verb: has, entity: message }, { verb: contains, entity: channel }, { verb: contains, entity: space }, { verb: has, entity: membership }, { verb: holds, entity: user }]
    when:
      - { entity: membership, fact: Role, is: Admin }
      - { entity: membership, fact: Banned, is: "No" }
  - related: [{ verb: has, entity: message }, { verb: contains, entity: channel }, { verb: contains, entity: space }, { verb: has, entity: membership }, { verb: holds, entity: user }]
    when:
      - { entity: membership, fact: Banned, is: "No" }
      - { entity: channel, fact: Members access, is: Read & Write }
  - related: [{ verb: has, entity: message }, { verb: contains, entity: channel }, { verb: has, entity: channel-permission }, { verb: has, entity: role }, { verb: holds, entity: user }]
    when:
      - { entity: channel-permission, fact: Access, is: Read & Write }
  - related: [{ verb: has, entity: message }, { verb: contains, entity: thread }, { verb: has, entity: channel }, { verb: contains, entity: space }, { verb: has, entity: membership }, { verb: holds, entity: user }]
    when:
      - { entity: membership, fact: Role, is: Admin }
      - { entity: membership, fact: Banned, is: "No" }
  - related: [{ verb: has, entity: message }, { verb: contains, entity: thread }, { verb: has, entity: channel }, { verb: contains, entity: space }, { verb: has, entity: membership }, { verb: holds, entity: user }]
    when:
      - { entity: membership, fact: Banned, is: "No" }
      - { entity: channel, fact: Members access, is: Read & Write }
  - related: [{ verb: has, entity: message }, { verb: contains, entity: thread }, { verb: has, entity: channel }, { verb: has, entity: channel-permission }, { verb: has, entity: role }, { verb: holds, entity: user }]
    when:
      - { entity: channel-permission, fact: Access, is: Read & Write }
references:
  - { kind: code, role: implementation, target: "packages/appserver/src/auth/writeAuth.ts#checkWriteAuth" }
---

# Only those who may write in a room react there

Reacting follows the same access as posting in the message's room.
