# cf orgs and spaces commands and output

Org/space management gets its own command names on Tanzu Hub — not just relabeled banner text on the classic `orgs`/`org`/`spaces`/`space` commands. See [../delete.md](../delete.md) for a captured `cf org-groups` / `cf delete-org-group` example this file's command names are based on.

## cf org-groups
```
$ cf org-groups
Getting org-groups as user-name...

name    foundation group   status
df-og   example-name       COMPLETED
sandbox example-name       FAILED
```
- `status` reflects the org group's own provisioning/reconciliation state on its foundation group, not anything about the apps/services inside it.

## cf org-group
```
$ cf org-group df-og
Getting info for org group df-og as user-name...

name:              df-og
guid:              df8c9a10-70a3-0000-a488-0000000000
foundation group:  example-name
status:            COMPLETED
quota:             default

Showing space groups:
   postfacto
   sandbox
```

## cf create-org-group
```
$ cf create-org-group df-og
Creating org group df-og as user-name...
OK

Assigning role OrgManager to user user-name in org group df-og...
OK

TIP: Use 'cf target -o "df-og"' to target new org group
```

## cf delete-org-group
```
$ cf delete-org-group df-og
Really delete the org group df-og? [yN]: y
Deleting org group df-og as user-name...
OK
```
- Deletes the org group and everything scoped under it (space groups, apps, service instances, routes) on its foundation group.

## cf rename-org-group
```
$ cf rename-org-group df-og df-og-2
Renaming org group df-og to df-og-2 as user-name...
OK
```

## cf space-groups
```
$ cf space-groups
Getting space groups in org group df-og as user-name...

name
postfacto
sandbox
```

## cf space-group
```
$ cf space-group postfacto
Getting info for space group postfacto in org group df-og as user-name...

name:              postfacto
guid:              e2b7f910-70a3-0000-a488-0000000010
org group:         df-og
foundation group:  example-name

Showing apps:
   postfacto-app
   postfacto-worker
```

## cf create-space-group
```
$ cf create-space-group postfacto
Creating space group postfacto in org group df-og as user-name...
OK

Assigning role SpaceManager to user user-name in org group df-og / space group postfacto as user-name...
OK

Assigning role SpaceDeveloper to user user-name in org group df-og / space group postfacto as user-name...
OK

TIP: Use 'cf target -o "df-og" -s "postfacto"' to target new space group
```

## cf delete-space-group
```
$ cf delete-space-group postfacto
Really delete the space group postfacto? [yN]: y
Deleting space group postfacto in org group df-og as user-name...
OK
```

## cf rename-space-group
```
$ cf rename-space-group postfacto postfacto-2
Renaming space group postfacto to postfacto-2 in org group df-og as user-name...
OK
```

## org group / space group vs org / space
- "org group"/"space group" are the hub's names for what a single foundation just calls "org"/"space" — every org group is tied to exactly one foundation group (see the `foundation group` field above), not a set spanning several. The hub isn't merging multiple foundations' orgs into one record; it's just where the org/space record lives when you're authenticated through Tanzu Hub instead of directly against a foundation.
- `create-org-group`/`rename-org-group`/`create-space-group`/`rename-space-group` are inferred by extension of the confirmed `org-groups`/`delete-org-group` naming pattern (see the delete.md reference above) — not independently confirmed. `org-groups`, `org-group`, and `delete-org-group` are the ones with a captured real example behind them.
- `cf target -f FOUNDATION_GROUP` (see [cf-login-target.md](cf-login-target.md)) pins commands to a specific foundation group — useful mainly for disambiguation or for foundation-scoped commands (apps, services, routes) rather than for the org-group/space-group commands themselves, which already resolve to one foundation group implicitly.
