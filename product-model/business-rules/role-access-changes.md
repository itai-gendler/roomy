---
appliesTo:
  - { type: entity, id: channel-permission, effect: changes }
permits:
  - related: [{ verb: has, entity: channel }, { verb: contains, entity: space }, { verb: has, entity: membership }, { verb: holds, entity: user }]
    when:
      - { entity: membership, fact: Role, is: Admin }
      - { entity: membership, fact: Banned, is: "No" }
references:
  - { kind: code, role: implementation, target: "packages/appserver/src/auth/writeAuth.ts#checkWriteAuth" }
---

# Only admins change a role's level in a channel

Switching a role between Read and Read & Write is an admin act.
