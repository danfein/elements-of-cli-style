# Domains and Routing

## Example Route
```
training-app-industrious-lemur-qf.apps.quiz-2722605.cf-app.com/example
```
- Hostname: training-app-industrious-lemur-qf
- Domain: apps.quiz-2722605.cf-app.com
- Path: /example

## cf routes
```
--- List ---
$ cf routes
Getting routes for org student-jfw5df / space default as student-jfw5df...

space     host                              domain                         port   path   protocol   app-protocol   apps           service instance
default   static-app-happy-sitatunga-yg     apps.zone-3924730.cf-app.com                 http       http1          static-app     
default   training-app-terrific-gelada-mh   apps.zone-3924730.cf-app.com                 http       http1          training-app   
```

## cf create route
```
--- Structure ---
$ cf create-route DOMAIN --hostname NAME

--- Example ---
$ cf create-route $CF_APP_DOMAIN --hostname $UNIQUE_HOSTNAME
Creating route training-app-student-jfw5df.apps.zone-3924730.cf-app.com for org student-jfw5df / space default as student-jfw5df...
Route training-app-student-jfw5df.apps.zone-3924730.cf-app.com has been created.
OK
```

## cf map route
Creating the route does not connect it to an app, that is done with map-route
If you map a route that does not exist, it will be created. 
```
$ cf map-route training-app $CF_APP_DOMAIN --hostname $UNIQUE_HOSTNAME
```

## cf unmap route
```
--- Unmap ---
$ cf unmap-route training-app $CF_APP_DOMAIN --hostname training-app-terrific-gelada-mh
Removing route training-app-terrific-gelada-mh.apps.zone-3924730.cf-app.com from app training-app in org student-jfw5df / space default as student-jfw5df...
OK

--- Verify ---
$ cf routes
Getting routes for org student-jfw5df / space default as student-jfw5df...

space     host                              domain                         port   path   protocol   app-protocol   apps   service instance
default   training-app-terrific-gelada-mh   apps.zone-3924730.cf-app.com                 http

--- Delete ---
$ cf delete-route $CF_APP_DOMAIN --hostname training-app-terrific-gelada-mh
This action impacts all apps using this route.
Deleting this route will make apps unreachable via this route.
Really delete the route training-app-terrific-gelada-mh.apps.zone-3924730.cf-app.com? [yN]: y
Deleting route training-app-terrific-gelada-mh.apps.zone-3924730.cf-app.com...
OK
```
- Note: if you delete without unmapping, the delete command will also unmap.

## cf route combo example
```
$ cf map-route first-push $CF_APP_DOMAIN -n $UNIQUE_HOSTNAME --path /kill
Creating route training-app-student-jfw5df.apps.zone-3924730.cf-app.com/kill for org student-jfw5df / space default as student-jfw5df...
OK

Mapping route training-app-student-jfw5df.apps.zone-3924730.cf-app.com/kill to app first-push in org student-jfw5df / space default as student-jfw5df...
OK
```

## cf domains
A shared domain is available to all users in all orgs of a Cloud Foundry deployment.  
A private domain can be added by Org Managers, and is scoped to an org by default.
DNS is managed with your DNS provider, outside of CF.  
TCP domains are an option, but only supported on shared domains.  
Domains can be internal or externally reachable.
```
--- List ---
$ cf domains
Getting domains in org student-pqvsjp as student-pqvsjp...

name                           availability   internal   protocols
apps.internal                  shared         true       http
apps.zone-3924730.cf-app.com   shared                    http

--- Create ---
cf create-private-domain $CF_ORG $PRIVATE_DOMAIN
Creating private domain student-pqvsjp.220af0b6.nip.io for org student-pqvsjp as student-pqvsjp...
OK

TIP: Domain 'student-pqvsjp.220af0b6.nip.io' is a private domain. Run 'cf share-private-domain' to share this domain with a different org.

--- Map ---
 $ cf map-route training-app $PRIVATE_DOMAIN --hostname training-app
Creating route training-app.student-pqvsjp.220af0b6.nip.io for org student-pqvsjp / space default as student-pqvsjp...
OK

Mapping route training-app.student-pqvsjp.220af0b6.nip.io to app training-app in org student-pqvsjp / space default as student-pqvsjp...
OK

--- Delete ---
cf delete-private-domain $PRIVATE_DOMAIN
Deleting private domain student-pqvsjp.220af0b6.nip.io as student-pqvsjp...
Deleting the private domain will remove associated routes which will make apps with this domain unreachable.
Really delete the private domain student-pqvsjp.220af0b6.nip.io? [yN]: y
Deleting private domain student-pqvsjp.220af0b6.nip.io as student-pqvsjp...
OK

TIP: Run 'cf domains' to view available domains.
```

## Orphaned Routes
```
cf delete-orphaned-routes
```