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
```