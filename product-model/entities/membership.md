---
references:
  - { kind: code, role: implementation, target: "packages/sdk/src/schema/events/space.ts#JoinSpace" }
  - { kind: code, role: implementation, target: "packages/appserver/src/auth/access.ts#spaceAccess" }
---

# Membership

A user's place in one space and the role they hold there. Leaving keeps the membership, so the space can be rejoined from the user's settings.

## Information kept

- **Role** — Admin, who runs the space's settings, structure and members, or Member
- **Banned** — Yes or No: whether an admin has banned the user from the space; a banned user can neither read nor write there and cannot rejoin
- **Joined at** — when the user joined the space
- **Update rhythm** — how much Roomy notifies the user about this space, when they chose one for it: Silent, Quiet, Engaged or Busy

## States

### Joined

The user is a member of the space.

### Left

The user left the space; it stays listed under their left spaces until they rejoin.
