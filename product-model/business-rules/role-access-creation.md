---
appliesTo:
  - { type: entity, id: channel-permission, effect: creates }
permits:
  - related: [{ verb: has, entity: channel }, { verb: contains, entity: space }, { verb: has, entity: membership }, { verb: holds, entity: user }]
    when:
      - { entity: membership, fact: Role, is: Admin }
      - { entity: membership, fact: Banned, is: "No" }
references:
  - { kind: code, role: implementation, target: "packages/appserver/src/auth/writeAuth.ts#checkWriteAuth" }
---

# Only admins give roles access to channels

Role access to a channel is set by the space's admins.
