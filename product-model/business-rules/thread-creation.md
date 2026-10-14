---
appliesTo:
  - { type: entity, id: thread, effect: creates }
permits:
  - related: [{ verb: has, entity: channel }, { verb: contains, entity: space }, { verb: has, entity: membership }, { verb: holds, entity: user }]
    when:
      - { entity: membership, fact: Role, is: Admin }
      - { entity: membership, fact: Banned, is: "No" }
  - related: [{ verb: has, entity: channel }, { verb: contains, entity: space }, { verb: has, entity: membership }, { verb: holds, entity: user }]
    when:
      - { entity: membership, fact: Banned, is: "No" }
      - { entity: channel, fact: Members access, is: Read & Write }
  - related: [{ verb: has, entity: channel }, { verb: has, entity: channel-permission }, { verb: has, entity: role }, { verb: holds, entity: user }]
    when:
      - { entity: channel-permission, fact: Access, is: Read & Write }
references:
  - { kind: code, role: implementation, target: "packages/appserver/src/auth/writeAuth.ts#checkWriteAuth" }
---

# Members who may write in a channel start its threads

Starting a thread forwards messages into it from the channel, so it needs write access to that channel: an admin, a member while the channel's Members access is Read & Write, or a member whose role has Read & Write there.
