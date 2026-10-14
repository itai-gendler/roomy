---
availability:
  - { place: roomy-app::spaces }
domain: invites
references:
  - { kind: code, role: implementation, target: "packages/app-lite/src/lib/mutations/invite.ts#createInvite" }
  - { kind: code, role: implementation, target: "packages/design/src/components/modals/InviteManager.svelte" }
---

# Create invite

Make a new invite link for an invite-only space.
