# Authentication

## NPM web auth
```
npm login --registry=https://usw1.packages.broadcom.com/artifactory/api/npm/project/ --auth-type=web
npm notice Log in on https://usw1.packages.broadcom.com/artifactory/api/npm/project/
Login at:
https://usw1.packages.broadcom.com/ui/auth-provider/npm?uuid=ABC123ABC123ABC123
Press ENTER to open in the browser...
Logged in on https://usw1.packages.broadcom.com/artifactory/api/npm/project/.
---

```

## CF CLI - set endpoing
```
~ cf api api.sys.dhaka.cf-app.com/ --skip-ssl-validation
Setting API endpoint to api.sys.dhaka.cf-app.com/...
OK

API endpoint:   https://api.sys.dhaka.cf-app.com/
API version:    3.215.0

Not logged in. Use 'cf login' or 'cf login --sso' to log in.
```

## CF CLI - sso login
```
~ cf login --sso
API endpoint: https://api.sys.dhaka.cf-app.com

Temporary Authentication Code ( Get one at https://login.sys.dhaka.cf-app.com/passcode ):
Authenticating...
OK


Select an org:
1. example-org
2. df-org

Org (enter to skip): 2
Targeted org dforg.

Targeted space dfspace.

API endpoint:   https://api.sys.dhaka.cf-app.com
API version:    3.215.0
user:           daniel.fein@broadcom.com
org:            dforg
space:          dfspace
```

## CF CLI - hub login
```
cf login
API endpoint: https://tanzuhub.lvn.broadcom.net

Listening on 127.0.0.1:0
Opening the browser window to complete the login
Log in by visiting this link:

    https://tpe-sb-be-tanzuhub.lvn.broadcom.net/auth/oauth/authorize?client_id=tp_cli_app&code_challenge=ABC123&code_challenge_method=ABC&redirect_uri=http%3A%2F%2F127.0.0.1%3A49759%2Fcallback&response_type=code&state=ABC123

    Optionally, paste your authorization code: [...]

Please press <ENTER> to continue

OK

Select an org group:
There are too many options to display; please type in the name.

Org group (enter to skip):df-og
Targeted org group df-og.

Select a space group:
1. df-agent
2. df-sg

Space group (enter to skip):2
Targeted space group df-sg.

API endpoint:   https://tanzuhub.lvn.broadcom.net
user:           tanzu_platform_admin
org group:      df-og
space group:    df-sg
No foundation group targeted. Commands that expect a foundation group may have it specified via flag, or by using 'cf target -f FOUNDATION_GROUP'
--
[i] Checking for CLI updates...

```

## CF CLI hub sso login
```
cf login --sso
API endpoint: https://tanzuhub.lvn.broadcom.net

Option '--sso' not supported by Tanzu Hub, use 'cf login' to connect to a foundation.
```