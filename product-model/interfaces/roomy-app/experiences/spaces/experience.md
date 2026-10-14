---
actors: [user]
access: authenticated
entryPoints:
  - roomy-app: /
references:
  - { kind: code, role: implementation, target: packages/app-lite/src/lib/components/layout/MainLayout.svelte }
  - { kind: code, role: implementation, target: packages/appserver/src/auth/access.ts }
---

# Spaces

Where signed-in users reach their spaces: reading and writing in channels and
threads, and — as each space's admins — shaping, moderating and federating the
space.
