---
appliesTo:
  - { type: entity, id: message, effect: creates }
permits:
  - related: [{ verb: contains, entity: channel }, { verb: contains, entity: space }, { verb: has, entity: membership }, { verb: holds, entity: user }]
    when:
      - { entity: membership, fact: Role, is: Admin }
      - { entity: membership, fact: Banned, is: "No" }
  - related: [{ verb: contains, entity: channel }, { verb: contains, entity: space }, { verb: has, entity: membership }, { verb: holds, entity: user }]
    when:
      - { entity: membership, fact: Banned, is: "No" }
      - { entity: channel, fact: Members access, is: Read & Write }
  - related: [{ verb: contains, entity: channel }, { verb: has, entity: channel-permission }, { verb: has, entity: role }, { verb: holds, entity: user }]
    when:
      - { entity: channel-permission, fact: Access, is: Read & Write }
  - related: [{ verb: contains, entity: thread }, { verb: has, entity: channel }, { verb: contains, entity: space }, { verb: has, entity: membership }, { verb: holds, entity: user }]
    when:
      - { entity: membership, fact: Role, is: Admin }
      - { entity: membership, fact: Banned, is: "No" }
  - related: [{ verb: contains, entity: thread }, { verb: has, entity: channel }, { verb: contains, entity: space }, { verb: has, entity: membership }, { verb: holds, entity: user }]
    when:
      - { entity: membership, fact: Banned, is: "No" }
      - { entity: channel, fact: Members access, is: Read & Write }
  - related: [{ verb: contains, entity: thread }, { verb: has, entity: channel }, { verb: has, entity: channel-permission }, { verb: has, entity: role }, { verb: holds, entity: user }]
    when:
      - { entity: channel-permission, fact: Access, is: Read & Write }
references:
  - { kind: code, role: implementation, target: "packages/appserver/src/auth/writeAuth.ts#checkWriteAuth" }
---

# Only those who may write in a room post there

An admin, a member while the channel's Members access is Read & Write, or a member whose role has Read & Write in the channel may post in it and in its threads. Forwards and the messages that start a thread are posts too.
