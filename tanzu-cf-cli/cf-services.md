# cf services commands and output

## cf services
```
$ cf services
Getting service instances in org group df-og / space group postfacto  as user-name...

name              offering                  plan              bound apps   last operation     broker   upgrade available   status
postfacto-redis   VMware Tanzu for Valkey   on-demand-cache                create succeeded            yes                 Running
```

## cf service
```
$ cf service postfacto-redis
Showing info of service postfacto-redis in org group df-og / space group postfacto  as user-name...

name:            postfacto-redis
guid:            4a3e7513-70a3-0000-a488-0000000000
type:            managed
broker:
offering:        VMware Tanzu for Valkey
plan:            on-demand-cache
tags:
offering tags:   on-demand, pivotal, redis
description:     VMware Tanzu for Valkey service to provide dedicated instances configured as a cache.
documentation:   https://techdocs.broadcom.com/tnz-for-valkey-on-cf
dashboard url:
status:          Running

Showing status of last operation:
   status:   create succeeded

Showing bound apps:
   There are no bound apps for this service instance.

Showing location:
   foundation:   example-name
   org:          df-og
   space:        postfacto

Showing upgrade status:
   There is an upgrade available for this service.
   TIP: You can upgrade using 'cf upgrade-service postfacto-redis'

```

## cf upgrade-service
```
Warning: This operation may be long running and will block further operations on the service instance until it's completed
Do you really want to upgrade the service instance postfacto-redis? [yN]:

Upgrading service instance postfacto-redis in org df-og / space postfacto as tanzu_platform_admin...

Upgrade in progress. Use 'cf services' or 'cf service postfacto-redis' to check operation status.
OK
```

