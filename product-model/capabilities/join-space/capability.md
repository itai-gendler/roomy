---
availability:
  - { place: roomy-app::spaces }
references:
  - { kind: code, role: implementation, target: "packages/app-lite/src/routes/join/[[spaceRef]]/+page.svelte" }
  - { kind: code, role: implementation, target: "packages/appserver/src/handlers/space.roomy.space.joinSpace.ts#joinSpaceHandler" }
---

# Join space

Become a member of a space from its link or an invite link, choosing an update rhythm for it on the way in. Invite-only spaces need a valid invite link; a space the user left is rejoined from their account settings.
