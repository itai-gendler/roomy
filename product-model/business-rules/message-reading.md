---
appliesTo:
  - { type: entity, id: message, effect: reads }
permits:
  - related: [{ verb: contains, entity: channel }, { verb: contains, entity: space }, { verb: has, entity: membership }, { verb: holds, entity: user }]
    when:
      - { entity: membership, fact: Role, is: Admin }
      - { entity: membership, fact: Banned, is: "No" }
  - related: [{ verb: contains, entity: channel }, { verb: contains, entity: space }, { verb: has, entity: membership }, { verb: holds, entity: user }]
    when:
      - { entity: membership, fact: Banned, is: "No" }
      - { entity: channel, fact: Members access, is-not: None }
  - related: [{ verb: contains, entity: channel }, { verb: has, entity: channel-permission }, { verb: has, entity: role }, { verb: holds, entity: user }]
    when:
      - { entity: channel-permission, fact: Access, present: true }
  - related: [{ verb: contains, entity: thread }, { verb: has, entity: channel }, { verb: contains, entity: space }, { verb: has, entity: membership }, { verb: holds, entity: user }]
    when:
      - { entity: membership, fact: Role, is: Admin }
      - { entity: membership, fact: Banned, is: "No" }
  - related: [{ verb: contains, entity: thread }, { verb: has, entity: channel }, { verb: contains, entity: space }, { verb: has, entity: membership }, { verb: holds, entity: user }]
    when:
      - { entity: membership, fact: Banned, is: "No" }
      - { entity: channel, fact: Members access, is-not: None }
  - related: [{ verb: contains, entity: thread }, { verb: has, entity: channel }, { verb: has, entity: channel-permission }, { verb: has, entity: role }, { verb: holds, entity: user }]
    when:
      - { entity: channel-permission, fact: Access, present: true }
  - unattended: true
references:
  - { kind: code, role: implementation, target: "packages/appserver/src/auth/access.ts#computeRoomAccess" }
  - { kind: code, role: implementation, target: "packages/appserver/src/push/evaluate.ts#evaluatePush" }
---

# Only those who may read a room see its messages

Admins, members of a channel whose Members access is not None, and members whose role reaches it read its messages and those of its threads; nobody is told of a room they cannot read.
