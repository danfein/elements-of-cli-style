# Context setting

## cf login
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

## cf target
```
$ cf target -s services
API endpoint:   https://api.sys.zone-3924730.cf-app.com
API version:    3.185.0
user:           student-ssxfh8
org:            student-ssxfh8
space:          services
```


## cf logout
```
cf logout
Logging out daniel.fein@broadcom.com...
OK
```

## Tanzu login
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

## Tanzu Projects
```
$ tanzu projects list
Listing projects from One Tanzu Integration org

  NAME                                 AGE  INTEGRATIONS
  Free Tier Project                    84d
  aria-test                            84d
  falcons-project-2                    84d
  jd-proj                              84d
  ...

$tanzu projects use new-horizon
✓ Successfully set project to new-horizon
```

## Tanzu Context
```
  $ tanzu context list
  NAME                                    ISACTIVE  TYPE   PROJECT      SPACE
  CMBU_TMM                                false     tanzu
  One_Tanzu_Integration-staging-3fb994fb  true      tanzu  new-horizon

$ tanzu context use
? Select a context  [Use arrows to move, type to filter]
> CMBU_TMM            (https://ucp.platform.tanzu.broadcom.com/org/2[org-id])
  One_Tanzu_Integration-staging-3fb994fb(https://ucp.platform-verify.tanzu.broadcom.com/org/[org-id]])

  [i] Successfully activated context 'One_Tanzu_Integration-staging-3fb994fb' (Type: tanzu, Project: new-horizon ([org-id]))

```
Danger of running long.