# Tanzu CF CLI reference

`cf` CLI output captured/representative for **VMware Tanzu Platform for Cloud Foundry via Tanzu Hub** — the multi-foundation product. Session banners say "org group" / "space group" instead of plain "org" / "space", and a **foundation group** selects which underlying CF foundation a command actually runs against. See [cf-login-target.md](cf-login-target.md) and the note at the bottom of [cf-orgs-spaces.md](cf-orgs-spaces.md) for how those concepts relate.

For classic single-foundation OSS Cloud Foundry, see [../cloud-foundry/](../cloud-foundry/) instead — same underlying `cf` CLI, different backend, different terminology.

## Contents
* [Login and targeting](cf-login-target.md) — `login`, `logout`, `target`, `api`, `auth`
* [Apps](cf-apps.md) — `apps`, `app`, `push`, `start`/`stop`/`restart`, `restage`, `scale`, `logs`, `env`, `ssh`, `buildpacks`/`stacks`
* [Services](cf-services.md) — `services`, `service`, `marketplace`, `create`/`bind`/`unbind`/`delete-service`, `upgrade-service`, service keys, `share`/`unshare-service`, `cups`
* [Routes and domains](cf-routes-domains.md) — `routes`, `create`/`map`/`unmap`/`delete-route`, `domains`
* [Orgs and spaces](cf-orgs-spaces.md) — `org-groups`/`org-group`, `space-groups`/`space-group`, create/delete/rename
* [Users and roles](cf-users-roles.md) — `org-group-users`, `space-group-users`, `set`/`unset-*-group-role`, `create-user`

## Status
Examples here are illustrative — built from documented `cf` CLI behavior, not captured verbatim from a live session (no live foundation was available while writing these). Flag names and command structure should be accurate; exact field names/formatting/message wording may drift slightly from what a real foundation prints. Treat as a design reference, verify against a live session before relying on exact output for pixel-perfect decisions.

Org/space management turned out to have its own command names on Tanzu Hub (`org-groups`, `delete-org-group`, etc.), not just relabeled banners on the classic `orgs`/`org` commands — confirmed against a real example already in [../delete.md](../delete.md) and corrected here accordingly. See the note at the bottom of [cf-orgs-spaces.md](cf-orgs-spaces.md) for what's confirmed vs. inferred by pattern.

Not yet covered here (lower priority — platform-operator-only surfaces): buildpacks/stacks admin, security groups, quotas, isolation segments, feature flags, metadata/labels, service brokers, network policies. Ask if you want any of these added.
