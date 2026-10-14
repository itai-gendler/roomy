---
appliesTo:
  - { type: entity, id: channel, effect: reads }
permits:
  - related: [{ verb: contains, entity: space }, { verb: has, entity: membership }, { verb: holds, entity: user }]
    when:
      - { entity: membership, fact: Role, is: Admin }
      - { entity: membership, fact: Banned, is: "No" }
  - related: [{ verb: contains, entity: space }, { verb: has, entity: membership }, { verb: holds, entity: user }]
    when:
      - { entity: membership, fact: Banned, is: "No" }
      - { fact: Members access, is-not: None }
      - { state: Active }
  - related: [{ verb: has, entity: channel-permission }, { verb: has, entity: role }, { verb: holds, entity: user }]
    when:
      - { entity: channel-permission, fact: Access, present: true }
      - { state: Active }
references:
  - { kind: code, role: implementation, target: "packages/appserver/src/auth/access.ts#computeRoomAccess" }
---

# Admins and members with access read a channel

Admins read every channel, archived ones included. A member reads an active channel unless its Members access is None, or when one of their roles gives them access. A banned user reads nothing in the space.
