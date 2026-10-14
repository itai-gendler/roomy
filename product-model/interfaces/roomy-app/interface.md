---
type: web
actors: [user]
entryPoints:
  - web: /
references:
  - { kind: code, role: implementation, target: packages/app-lite/src/routes/+layout.svelte }
  - { kind: code, role: implementation, target: packages/app-lite/src/lib/components/layout/auth-guard.svelte.ts }
  - { kind: code, role: context, target: packages/app-lite/src/lib/config.ts }
---

# Roomy app

The Roomy app in the browser, where people sign in with their AT Protocol
account and take part in their spaces. Everything past signing in needs a
session.
