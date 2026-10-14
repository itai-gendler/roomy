---
appliesTo:
  - { type: entity, id: channel-permission, effect: removes }
permits:
  - related: [{ verb: has, entity: channel }, { verb: contains, entity: space }, { verb: has, entity: membership }, { verb: holds, entity: user }]
    when:
      - { entity: membership, fact: Role, is: Admin }
      - { entity: membership, fact: Banned, is: "No" }
references:
  - { kind: code, role: implementation, target: "packages/appserver/src/auth/writeAuth.ts#checkWriteAuth" }
---

# Only admins take a role's channel access away

Setting a role back to None is an admin act.
