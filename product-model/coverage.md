---
scope: The Roomy web client, the appserver behavior it relies on, and the SDK event schemas.
method: Static inspection of source, lexicons, tests and documentation at the pinned commit.
covered:
  - description: Web client routes, components, queries and mutations for spaces, rooms, chat, settings and accounts.
    paths:
      - "packages/app-lite/src/routes/"
      - "packages/app-lite/src/lib/components/"
      - "packages/app-lite/src/lib/mutations/"
      - "packages/app-lite/src/lib/queries/"
  - description: Appserver authorization, XRPC handlers for spaces, rooms, messages, members, invites, federation and push.
    paths:
      - "packages/appserver/src/auth/"
      - "packages/appserver/src/handlers/"
      - "packages/appserver/src/push/"
  - description: SDK event schemas and their materialization.
    paths:
      - "packages/sdk/src/schema/events/"
      - "packages/sdk/src/operations/"
  - description: Shared design components that carry product wording for messages, permissions and invites.
    paths:
      - "packages/design/src/components/content/thread/message/"
      - "packages/design/src/components/ui/PermissionEditor.svelte"
      - "packages/design/src/components/modals/"
exclusions:
  - description: Appserver storage, materialization pipeline, caches, sync transport, telemetry and workers.
    paths:
      - "packages/appserver/src/db/"
      - "packages/appserver/src/materialization/"
      - "packages/appserver/src/cache/"
      - "packages/appserver/src/sync/"
      - "packages/appserver/src/invalidation/"
      - "packages/appserver/src/telemetry/"
      - "packages/appserver/src/workers/"
      - "packages/appserver/src/streams/"
  - description: Design system primitives, icons, fonts and storybook.
    paths:
      - "packages/design/src/components/ui/"
      - "packages/design/src/icons/"
  - description: Client caching, offline persistence, telemetry and link routing.
    paths:
      - "packages/app-lite/src/lib/cache-store.ts"
      - "packages/app-lite/src/lib/telemetry/"
      - "packages/app-lite/src/lib/external-link-handler.ts"
      - "packages/sdk/src/cache/"
      - "packages/sdk/src/browser/"
  - description: Deployment, local stacks and observability configuration.
    paths:
      - "deploy/"
      - "pds/"
      - "scripts/"
      - "compose.yaml"
      - "Caddyfile"
      - "netlify.toml"
  - description: End-to-end test harness and performance probes.
    paths:
      - "packages/app-lite/e2e/"
      - "packages/appserver/perf/"
unmapped:
  - description: Discord bridge service and its settings page, a Roomy Pro feature.
    paths:
      - "packages/discord-bridge/"
      - "packages/app-lite/src/routes/[space]/settings/discord-bridge/"
  - description: Voice rooms and calls behind the voice-chat flag.
    paths:
      - "packages/appserver/src/voice/"
      - "packages/app-lite/src/lib/voice/"
      - "packages/app-lite/src/lib/components/voice/"
      - "packages/sdk/src/schema/events/voice.ts"
  - description: Search of messages and rooms behind the search flag.
    paths:
      - "packages/appserver/src/search/"
      - "packages/app-lite/src/routes/search/"
      - "packages/app-lite/src/routes/[space]/search/"
      - "packages/app-lite/src/routes/[space]/[room]/search/"
  - description: Links view behind the links-view flag.
    paths:
      - "packages/app-lite/src/lib/components/thread/LinksView.svelte"
      - "packages/appserver/src/handlers/space.roomy.room.getLinks.ts"
      - "packages/appserver/src/handlers/space.roomy.space.getLinks.ts"
  - description: Roomy Pro subscription, billing and the Pro role reconciliation.
    paths:
      - "packages/appserver/src/billing/"
      - "packages/app-lite/src/routes/user/settings/subscription/"
  - description: Space handles, Bluesky account integration and the space policy reset through the Arbiter.
    paths:
      - "packages/app-lite/src/routes/[space]/settings/handle/"
      - "packages/app-lite/src/routes/[space]/settings/integrations/"
      - "packages/appserver/src/arbiter/"
      - "packages/appserver/src/handlers/space.roomy.space.setHandle.ts"
      - "packages/appserver/src/handlers/space.roomy.space.updatePolicy.ts"
  - description: Access-scope settings, user blocks, Semble cards and Bluesky direct messages behind their flags.
    paths:
      - "packages/app-lite/src/routes/user/settings/scopes/"
      - "packages/app-lite/src/lib/mutations/blocks.ts"
      - "packages/app-lite/src/lib/mutations/semble-personal.ts"
      - "packages/app-lite/src/lib/mutations/space-card.ts"
      - "packages/appserver/src/handlers/space.roomy.user.refreshBlocks.ts"
  - description: Pages (document rooms) and their edits, which the SDK and appserver keep but the web client offers no way to create or edit.
    paths:
      - "packages/sdk/src/schema/events/page.ts"
  - description: Web Tiles rendering and calendar links.
    paths:
      - "packages/app-lite/src/routes/tiles/"
      - "packages/app-lite/src/lib/tiles/"
      - "packages/sdk/src/schema/events/calendar.ts"
  - description: Operator administration endpoints, feature flags and the API documentation and admin dashboard site.
    paths:
      - "packages/appserver/src/handlers/space.roomy.admin.clearFlag.ts"
      - "packages/appserver/src/admin.ts"
      - "packages/appserver/src/featureFlags.ts"
      - "packages/docs/"
  - description: Command-line client.
    paths:
      - "packages/cli/"
  - description: Native desktop and mobile shell around the web client.
    paths:
      - "packages/app-lite/src-tauri/"
limitations:
  - description: The XRPC interface reached by other clients; whether it is a supported product interface beside the web client could not be settled from the code.
    paths:
      - "packages/appserver/lexicons/"
      - "packages/sdk/src/schemas/"
---

# Coverage
