# cf login and target commands and output

## cf login
```
$ cf login -a https://tanzuhub.lvn.company.net
API endpoint: https://tanzuhub.lvn.company.net

To continue, open the following URL in your browser and log in:

    https://tanzuhub.lvn.company.net/login/oauth/authorize?response_type=code&client_id=cf&redirect_uri=...

Please press <ENTER> to continue...

Authenticating...
OK

Select an org group:
There are too many options to display; please type in the name.

Org group: df-og
Targeted org group df-og.

Select a space group:
1. postfacto
2. sandbox

Space group (enter to skip): 1
Targeted space group postfacto.

API endpoint:      https://tanzuhub.lvn.company.net
API version:       3.197.0
user:              user-name
org group:         df-og
space group:       postfacto
foundation group:  No foundation group targeted, use 'cf target -f FOUNDATION_GROUP'
```
- browser step is skipped if a valid SSO session already exists.
- "too many options" replaces the numbered org group list once the account has more org groups than fit on screen; space groups still list normally.

## cf login --sso
```
$ cf login --sso -a https://tanzuhub.lvn.company.net
Option '--sso' not supported by Tanzu Hub, use 'cf login' to connect to a foundation.
FAILED
```
- `--sso` is a classic single-foundation `cf` flag; Tanzu Hub always uses the browser OAuth flow from plain `cf login`.

## cf logout
```
$ cf logout
Logging out...
OK
```

## cf target
```
$ cf target
API endpoint:      https://tanzuhub.lvn.company.net
API version:       3.197.0
user:              user-name
org group:         df-og
space group:       postfacto
foundation group:  example-name
```
- foundation group only appears once explicitly targeted; see `cf target -f`.

## cf target -o / --org-group, -s / --space-group
```
$ cf target -o another-og
API endpoint:      https://tanzuhub.lvn.company.net
API version:       3.197.0
user:              user-name
org group:         another-og
space group:       No space group targeted, use 'cf target -s SPACE_GROUP'
foundation group:  example-name
```
- note: switching org group clears the previously targeted space group; foundation group target is unaffected.

```
$ cf target -s sandbox
API endpoint:      https://tanzuhub.lvn.company.net
API version:       3.197.0
user:              user-name
org group:         another-og
space group:       sandbox
foundation group:  example-name
```

```
$ cf target -o df-og -s postfacto
API endpoint:      https://tanzuhub.lvn.company.net
API version:       3.197.0
user:              user-name
org group:         df-og
space group:       postfacto
foundation group:  example-name
```
- `-o`/`--org-group` and `-s`/`--space-group` can be combined in a single command to avoid the intermediate no-space-group state.

## cf target -f / --foundation-group
```
$ cf target -f example-name
API endpoint:      https://tanzuhub.lvn.company.net
API version:       3.197.0
user:              user-name
org group:         df-og
space group:       postfacto
foundation group:  example-name
```

```
$ cf target -f unknown-foundation
Foundation group 'unknown-foundation' not found.
FAILED
```
- foundation group is Tanzu Hub-specific: it selects which underlying CF foundation a command actually runs against, independent of org group / space group.

## cf api
```
$ cf api
api endpoint:   https://tanzuhub.lvn.company.net
api version:    3.197.0

$ cf api https://tanzuhub.lvn.company.net
Setting API endpoint to https://tanzuhub.lvn.company.net...
OK

api endpoint:   https://tanzuhub.lvn.company.net
api version:    3.197.0
```
- one hub URL for every foundation group; there's no per-foundation API endpoint to switch between.

## cf auth
```
$ cf auth user-name@company.com "$CF_PASSWORD"
API endpoint: https://tanzuhub.lvn.company.net
Authenticating...
OK
```
```
$ CF_USERNAME=user-name@company.com CF_PASSWORD=*** cf auth
API endpoint: https://tanzuhub.lvn.company.net
Authenticating...
OK
```
- for scripts/CI; does not set org group, space group, or foundation group targets. Run `cf target -o ORG_GROUP -s SPACE_GROUP -f FOUNDATION_GROUP` afterward.

## Errors

```
--- foundation group required, none targeted ---
$ cf ssh training-app
No foundation group targeted. Commands that expect a foundation group may have it specified via flag, or by using 'cf target -f FOUNDATION_GROUP'.
FAILED

--- org group / space group required, none targeted ---
$ cf apps
No org group or space group targeted, use 'cf target -o ORG_GROUP -s SPACE_GROUP' to target an org group and space group.
FAILED

--- unknown org group ---
$ cf target -o bad-org-group
Org group 'bad-org-group' not found.
FAILED

--- unknown foundation group ---
$ cf target -f bad-foundation-group
Foundation group 'bad-foundation-group' not found.
FAILED
```
