# cf routes and domains commands and output

## cf routes
```
$ cf routes
Getting routes for org group df-og / space group postfacto  as user-name...

space       host                              domain                          port   path   protocol   app-protocol   apps            service instance
postfacto   training-app-jubilant-quokka-lm   apps.example-name.cf-app.com           /api   http       http1          training-app
postfacto   postfacto-api-solemn-heron-rx     apps.example-name.cf-app.com                  http       http1          postfacto-api
```
- No dedicated single-route detail command exists; filter this table or use `cf check-route` to test for a specific route.
- Empty `service instance` column means the route isn't bound to a route service.

## cf create-route
```
$ cf create-route apps.example-name.cf-app.com --hostname training-app-jubilant-quokka-lm
Creating route training-app-jubilant-quokka-lm.apps.example-name.cf-app.com for org group df-og / space group postfacto  as user-name...
Route training-app-jubilant-quokka-lm.apps.example-name.cf-app.com has been created.
OK

$ cf create-route apps.example-name.cf-app.com --hostname training-app-jubilant-quokka-lm --path /api
Creating route training-app-jubilant-quokka-lm.apps.example-name.cf-app.com/api for org group df-og / space group postfacto  as user-name...
Route training-app-jubilant-quokka-lm.apps.example-name.cf-app.com/api has been created.
OK
```
- Creating a route does not attach it to an app; that requires `cf map-route`.

## cf map-route
```
$ cf map-route training-app apps.example-name.cf-app.com --hostname training-app-jubilant-quokka-lm
Mapping route training-app-jubilant-quokka-lm.apps.example-name.cf-app.com to app training-app in org group df-og / space group postfacto  as user-name...
OK
```
```
--- Mapping a route that doesn't exist yet ---
$ cf map-route training-app apps.example-name.cf-app.com --hostname training-app-fresh-otter-zq
Creating route training-app-fresh-otter-zq.apps.example-name.cf-app.com for org group df-og / space group postfacto  as user-name...
OK

Mapping route training-app-fresh-otter-zq.apps.example-name.cf-app.com to app training-app in org group df-og / space group postfacto  as user-name...
OK
```
- If the route doesn't already exist, `map-route` creates it first, then maps it — two separate `OK` blocks.

## cf unmap-route
```
$ cf unmap-route training-app apps.example-name.cf-app.com --hostname training-app-jubilant-quokka-lm
Removing route training-app-jubilant-quokka-lm.apps.example-name.cf-app.com from app training-app in org group df-og / space group postfacto  as user-name...
OK
```
- Detaches the route from the app only; the route itself still exists and can be mapped elsewhere.

## cf delete-route
```
$ cf delete-route apps.example-name.cf-app.com --hostname training-app-jubilant-quokka-lm
This action impacts all apps using this route.
Deleting this route will make apps unreachable via this route.
Really delete the route training-app-jubilant-quokka-lm.apps.example-name.cf-app.com? [yN]: y
Deleting route training-app-jubilant-quokka-lm.apps.example-name.cf-app.com...
OK
```
- `-f` skips the confirmation prompt.
- If the route is still mapped to an app, deleting it also unmaps it — no separate unmap step needed.

## cf check-route
```
$ cf check-route apps.example-name.cf-app.com --hostname training-app-jubilant-quokka-lm
Checking for route...
Route training-app-jubilant-quokka-lm.apps.example-name.cf-app.com does exist

$ cf check-route apps.example-name.cf-app.com --hostname training-app-fresh-otter-zq
Checking for route...
Route training-app-fresh-otter-zq.apps.example-name.cf-app.com does not exist
```

## cf domains
```
$ cf domains
Getting domains in org group df-og / space group postfacto  as user-name...

name                            availability   internal   protocols
apps.internal                   shared         true       http
apps.example-name.cf-app.com    shared                    http
df-og.example-name.cf-app.com   private                   http
```
- Shared domains are visible to every org group on the foundation.
- Private domains are scoped to their owning org group unless shared with `cf share-private-domain`.

## cf create-private-domain
```
$ cf create-private-domain df-og df-og.example-name.cf-app.com
Creating private domain df-og.example-name.cf-app.com for org group df-og as user-name...
OK

TIP: Domain 'df-og.example-name.cf-app.com' is a private domain. Run 'cf share-private-domain' to share this domain with a different org group.
```
- Command syntax is still `cf create-private-domain ORG DOMAIN`; on Tanzu Hub the ORG argument value is the org group name.

## cf delete-private-domain
```
$ cf delete-private-domain df-og.example-name.cf-app.com
Deleting the private domain will remove associated routes which will make apps with this domain unreachable.
Really delete the private domain df-og.example-name.cf-app.com? [yN]: y
Deleting private domain df-og.example-name.cf-app.com as user-name...
OK
```
- Takes only the domain name — no org group argument.

## cf delete-orphaned-routes
```
$ cf delete-orphaned-routes
Really delete orphaned routes? [yN]: y
Getting routes as user-name...
Deleting route postfacto-api-solemn-heron-rx.apps.example-name.cf-app.com...
OK
```
- Only removes routes with zero bound apps; safe to run as periodic cleanup.
