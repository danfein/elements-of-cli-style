# Cloud Foundry CLI reference

`cf` CLI output for classic, single-foundation Cloud Foundry (plain "org" / "space", one API endpoint per foundation).

For `cf` against VMware Tanzu Platform for Cloud Foundry via Tanzu Hub (multi-foundation, "org group" / "space group", foundation groups), see [../tanzu-cf-cli/](../tanzu-cf-cli/) instead.

## cf CLI
* [Full command reference](cf-cli.md) — `cf help -a` output, all command groups
* [Login and auth](login.md) — `login`, `auth`, target errors
* [Target](target.md) — `cf target`
* [Apps](cf-apps.md) — `apps`, `app`
* [Push](cf-push.md) — getting-started walkthrough, sub-step deploy (create-app/package/stage/set-droplet)
* [Restage](restage.md)
* [Rollback](rollback.md) — manual droplet rollback, revisions
* [Domains and routing](domains-routing.md)
* [Services](services.md) — services, marketplace, bind/unbind, service keys, sharing, user-provided services
* [Marketplace](marketplace.md) — marketplace + genai service walkthrough
* [Users](users.md) — org-users, space-users
* [Plugins](plugins.md) — installing/using cf CLI plugins

## Related tools
* [cf-mgmt](cf-mgmt.md) — org/space/user/quota automation CLI
* [om (Ops Manager CLI)](om-cli.md)
* [UAA / uaac](uaa-uaac.md)
* [ADBR plugin](adbr.md) — application data backup and restore
