---
appliesTo:
  - { type: entity, id: membership, effect: creates }
  - { type: entity, id: invite }
references:
  - { kind: code, role: implementation, target: "packages/appserver/src/handlers/space.roomy.space.joinSpace.ts#joinSpaceHandler" }
---

# Joining an invite-only space needs a valid invite link

A public space admits anyone signed in. An invite-only space admits only someone holding an invite link that has not been revoked, and a banned user is never admitted.
