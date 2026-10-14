---
appliesTo:
  - { type: entity, id: space, effect: changes }
permits:
  - related: [{ verb: has, entity: membership }, { verb: holds, entity: user }]
    when:
      - { entity: membership, fact: Role, is: Admin }
      - { entity: membership, fact: Banned, is: "No" }
references:
  - { kind: code, role: implementation, target: "packages/appserver/src/auth/writeAuth.ts#checkWriteAuth" }
---

# Only admins change a space's settings

Name, description, picture, join policy, member invites, suggestions and the order of categories are the admins' to set.
