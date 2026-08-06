# cf users and roles commands and output

Command names below follow the confirmed `org-groups`/`delete-org-group` pattern from [../delete.md](../delete.md) — see the note at the bottom of [cf-orgs-spaces.md](cf-orgs-spaces.md). The `-group` renames here (`org-group-users`, `set-org-group-role`, etc.) are inferred by extension of that pattern, not independently confirmed.

## cf org-group-users
```
$ cf org-group-users df-og
Getting users in org group df-og as user-name...

ORG MANAGER
  tanzu_platform_admin (uaa)
  user-name (uaa)

BILLING MANAGER
  No BILLING MANAGER found

ORG AUDITOR
  No ORG AUDITOR found
```

## cf space-group-users
```
$ cf space-group-users df-og postfacto
Getting users in org group df-og / space group postfacto as user-name...

SPACE MANAGER
  tanzu_platform_admin (uaa)

SPACE DEVELOPER
  tanzu_platform_admin (uaa)
  user-name (uaa)

SPACE SUPPORTER
  No SPACE SUPPORTER found

SPACE AUDITOR
  No SPACE AUDITOR found
```

## cf set-org-group-role
```
$ cf set-org-group-role tanzu_platform_admin df-og OrgManager
Assigning role OrgManager to user tanzu_platform_admin in org group df-og as user-name...
OK
```
- ROLE arg is the camel-case name (OrgManager, BillingManager, OrgAuditor); the confirmation line echoes it back verbatim, not the ALL-CAPS display label used in `cf org-group-users`.
- Since an org group resolves to one foundation group (see cf-orgs-spaces.md), the role applies there — no cross-foundation propagation question to worry about.

## cf unset-org-group-role
```
$ cf unset-org-group-role tanzu_platform_admin df-og OrgManager
Removing role OrgManager from user tanzu_platform_admin in org group df-og as user-name...
OK
```

## cf set-space-group-role
```
$ cf set-space-group-role user-name df-og postfacto SpaceDeveloper
Assigning role SpaceDeveloper to user user-name in org group df-og / space group postfacto as user-name...
OK
```

## cf unset-space-group-role
```
$ cf unset-space-group-role user-name df-og postfacto SpaceDeveloper
Removing role SpaceDeveloper from user user-name in org group df-og / space group postfacto as user-name...
OK
```

## cf create-user
```
$ cf create-user newuser@example.com --origin sso
Creating user newuser@example.com...
OK

TIP: Assign roles with 'cf set-org-group-role' and 'cf set-space-group-role'
```
- `--origin` picks the UAA identity provider (e.g. `sso`, `ldap`); omit it for an internal UAA user and supply a password instead.
- A created user has no roles anywhere until `set-org-group-role`/`set-space-group-role` is run.
- Not renamed — user creation is a UAA-level operation, not scoped to an org group/space group.

## cf delete-user
```
$ cf delete-user newuser@example.com
Really delete the user newuser@example.com and their given resources? [yN]: y
Deleting user newuser@example.com...
OK
```
- `-f` skips the confirmation prompt.
- Deletes the UAA user record outright -- this is not scoped to df-og, it removes org/space role membership everywhere the user had any.
