# Logging in to cf
For humans
```
cf login
cf login --sso
```
- Credenials are provided interactivly, or (less ideally) via flags
- The CLI will attempt to set the org and space targets

## Automation friendly login
```
cf auth
```
- Creds are provided via envars
- The CLI will not set your target

## Helper Prompts
```
$ cf login ...
Authenticating...
OK


Select an org:
1. name-of-org
2. another-org

Org (enter to skip): 2
Targeted org another-org.

Select a space:
1. df-test
2. space2

Space (enter to skip):
API endpoint:   https://api.sys.url.cf-app.com
API version:    3.197.0
user:           daniel.fein@company.com
org:            FeinDaniel-Org
space:          No space targeted, use 'cf target -s SPACE'


--- if one org available ===

$ cf login ...
Authenticating...
OK

API endpoint:   https://api.bosh-lite.com (API version: 3.43.0)
User:           admin
org:            availble-org-name
No space targeted, use 'cf target -s SPACE'



--- if no org available ---

$ cf login ...
Authenticating...
OK

API endpoint:   https://api.bosh-lite.com (API version: 2.43.0)
User:           admin
No org or space targeted, use 'cf target -o ORG -s SPACE'


--- if one space available ---
$ cf target -o NAME
API endpoint:   https://api.sys.dhaka.cf-app.com
API version:    3.197.0
user:           daniel.fein@broadcom.com
org:            NAME
space:          df-test
```

## Error

Running command without scope set
```
--- org and space not set ---

$ cf push

No org and space targeted, use 'cf target -o ORG -s SPACE' to target an org and space
FAILED

$ cf target
API endpoint:   https://api.sys.url.cf-app.com
API version:    3.197.0
user:           daniel.fein@name.com
No org or space targeted, use 'cf target -o ORG -s SPACE'

--- space not set ---

$ cf push

No space targeted, use 'cf target -s SPACE' to target a space.
FAILED

$ cf target
API endpoint:   https://api.sys.url.cf-app.com
API version:    3.197.0
user:           daniel.fein@name.com

```

Running tanzu commands against cf endpoint
```
$ cf target -f name
you need to be connected to Tanzu Hub to target a foundation group
FAILED
```

Invalid values
```
--- org ---
$ cf target -o bad-name
Organization 'bad-name' not found.
FAILED

--- space ---
$ cf target -o name -s bad-name
Space 'bad-name' not found.
FAILED

```