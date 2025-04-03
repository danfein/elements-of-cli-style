# Context setting

## cf CLI login
```
$ cf login --sso
API endpoint: https://api.sys.dhaka.cf-app.com

Temporary Authentication Code ( Get one at https://login.sys.dhaka.cf-
app.com/passcode ):
Authenticating...
OK


Select an org:
1. acme-fitness
2. alisterlewisbowen-org

Org (enter to skip): 1
Targeted org acme-fitness.

Select a space:
1. acme-fitness-space
2. example-two

Space (enter to skip): 1
Targeted space acme-fitness-space.

API endpoint:   https://api.sys.dhaka.cf-app.com
API version:    3.179.0
user:           daniel.fein@broadcom.com
org:            acme-fitness
space:          acme-fitness-space
```

## cf CLI logout
```
cf logout
Logging out daniel.fein@broadcom.com...
OK
```

## Tanzu CLI login
```
 $ tanzu login
[i] Opening the browser window to complete the login
Log in by visiting this link:

    https://console.tanzu.broadcom.com/csp/gateway/discovery?client_id=tanzu-cli-client-id&code_challenge=[url truncated]

    Optionally, paste your authorization code: [...]


[ok] Successfully logged into 'CMBU TMM' organization and created a tanzu context

[!] WARNING: While authenticated to organization 'CMBU TMM', there are insufficient permissions to access
the Tanzu Platform for Kubernetes service. Please ensure correct organization authentication and access permissions

```
