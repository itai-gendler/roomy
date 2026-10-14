---
availability:
  - { place: roomy-app::welcome }
references:
  - { kind: code, role: implementation, target: "packages/app-lite/src/lib/auth.svelte.ts" }
  - { kind: code, role: implementation, target: "packages/app-lite/src/lib/components/auth/LoginModal.svelte" }
  - { kind: doc, role: context, target: "packages/appserver/docs/authentication.md" }
---

# Log in

Sign in with an existing AT Protocol account by its handle, approving Roomy at the person's own account server.
