---
entities:
  - { entity: invite, shows: [Link] }
entryPoints:
  - roomy-app: "/{space}/settings/invites"
references:
  - { kind: code, role: implementation, target: "packages/app-lite/src/routes/[space]/settings/invites/+page.svelte" }
  - { kind: code, role: implementation, target: "packages/app-lite/src/lib/components/InviteModal.svelte" }
---

# Invites

The invite links of an invite-only space.
