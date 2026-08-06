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

Upgrading service instance postfacto-redis in org df-og / space postfacto as user-name...

Upgrade in progress. Use 'cf services' or 'cf service postfacto-redis' to check operation status.
OK
```

## cf marketplace
```
cf marketplace
Getting all service offerings from marketplace in org group df-og / space group postfacto  as user-name...

offering                plans                                                                                              description                                                                                                                                           broker
ai-models               ai-dev, ollama3.1                                                                                  Integrations with generative AI models via an AI API proxy that routes to configured LLMs.                                                            genai-service
app-autoscaler          standard                                                                                           Scales bound applications in response to load                                                                                                         app-autoscaler
block-storage           on-demand-1024                                                                                     Block storage volumes                                                                                                                                 blockstoragebroker
credhub                 default                                                                                            Stores configuration parameters securely in CredHub                                                                                                   credhub-broker
kafka                   large, medium, small                                                                               VMware Tanzu for Apache Kafka on Tanzu Platform service provides dedicated instances of this high-performance distributed event streaming platform.   kafka-service-broker
mcp-gateway             gateway                                                                                            MCP Gateway enables management and observability of MCP servers.                                                                                      genai-service
p-cloudcache            dev-plan, extra-small, mk015214-test, small                                                        VMware Tanzu GemFire offers the ability to deploy a VMware GemFire cluster as a service in Tanzu Platform.                                            cloudcache-broker
p-dataflow-messaging    proxy                                                                                              Proxies to the Spring Cloud Data Flow messaging service instance                                                                                      p-dataflow
p-dataflow-relational   proxy                                                                                              Proxies to the Spring Cloud Data Flow datastore service instance                                                                                      p-dataflow
p-identity              tanzu-service-publisher                                                                            Provides identity capabilities via UAA as a Service                                                                                                   identity-service-broker
p-redis                 shared-vm                                                                                          Valkey service to provide pre-provisioned instances configured as a datastore, running on a shared VM.                                                p-redis
p.config-server         standard                                                                                           Service to provide configuration to applications at runtime.                                                                                          scs-service-broker
p.gateway               standard                                                                                           API Gateway                                                                                                                                           scg-service-broker
p.mysql                 db-medium, db-small, st-msql-test, tanzu-custom-plan                                               Dedicated instances of VMware Tanzu for MySQL                                                                                                         dedicated-mysql-broker
p.rabbitmq              on-demand-plan                                                                                     VMware Tanzu RabbitMQ provides dedicated instances of this high-performance multi-protocol messaging broker                                           rabbitmq-odb
p.redis                 on-demand-cache                                                                                    VMware Tanzu for Valkey service to provide dedicated instances configured as a cache.                                                                 redis-odb
p.service-registry      standard                                                                                           Service to provide service discovery and registration for applications                                                                                scs-service-broker
postgres                demo-plan, lw-custom-plan, postgres-db-large, postgres-db-medium, postgres-db-micro, st-fdb-plan   VMware Tanzu for Postgres on Tanzu Platform service to provide dedicated instances configured as database.                                            postgres-odb

TIP: Use 'cf marketplace -e SERVICE_OFFERING' to view descriptions of individual plans of a given service offering.
```
## cf marketplace -e (details)
```
$ cf marketplace -e p.mysql
Getting service plan information for service offering p.mysql in org group df-og / space group postfacto  as user-name...

broker: dedicated-mysql-broker
   description:      Dedicated instances of VMware Tanzu for MySQL
   documentation:    https://techdocs.broadcom.com/tnz-mysql-for-cf
   support:          https://support.broadcom.com/group/ecx/downloads
   contact:
   backing app:

   plans:
      name                description                                             free or paid   costs   managed   self-managed
      db-medium           This plan provides a medium dedicated MySQL instance.   free
      db-small            This plan provides a small dedicated MySQL instance.    free
      st-msql-test        This plan provides a small dedicated MySQL instance.    free                             backups, restore
      tanzu-custom-plan   This plan provides a small dedicated MySQL instance.    free                             backups, restore
```
- "offering" is the service name; "plans" are the flavors of that offering.

## cf create-service
```
$ cf create-service p.mysql db-small training-app-db
Creating service instance training-app-db in org group df-og / space group postfacto  as user-name...

Service instance training-app-db created.
OK
```
- Returns once the request is accepted, not once the instance is ready — add `--wait` to block until provisioning finishes.

## cf bind-service
```
$ cf bind-service training-app training-app-db
Binding service instance training-app-db to app training-app in org group df-og / space group postfacto  as user-name...
OK

TIP: Use 'cf restage training-app' to ensure your env variable changes take effect
```

## cf unbind-service
```
$ cf unbind-service training-app training-app-db
Unbinding app training-app from service training-app-db in org group df-og / space group postfacto  as user-name...
OK
```

## cf delete-service
```
$ cf delete-service training-app-db
This action impacts all resources scoped to this service instance, including service bindings, service keys and route bindings.
This will remove the service instance from any spaces where it has been shared.
Really delete the service instance training-app-db? [yN]: y
Deleting service instance training-app-db in org group df-og / space group postfacto  as user-name...

Service instance training-app-db deleted.
OK
```

## Service keys
Used to connect to a service instance directly; on-platform apps get credentials via binding instead.
```
--- Create ---
$ cf create-service-key training-app-db monitoring-creds
Creating service key monitoring-creds for service instance training-app-db as user-name...
OK

--- List ---
$ cf service-keys training-app-db
Getting keys for service instance training-app-db as user-name...

name
monitoring-creds

--- View ---
$ cf service-key training-app-db monitoring-creds
Getting key monitoring-creds for service instance training-app-db as user-name...

{
  "credentials": {
    "hostname": "postfacto-redis.example-name.svc",
    "password": "REDACTED",
    "port": "6379",
    "uri": "redis://:REDACTED@postfacto-redis.example-name.svc:6379"
  }
}

--- Delete ---
$ cf delete-service-key training-app-db monitoring-creds
Really delete the service key monitoring-creds ? [yN]: y
Deleting key monitoring-creds for service instance training-app-db as user-name...
OK
```

## cf share-service / cf unshare-service
Service sharing across space groups must be enabled globally by a platform admin; a shared instance can't be renamed or updated, and deleting it from any space it's shared into deletes it everywhere.
```
--- share ---
$ cf share-service training-app-db -s sandbox
Sharing service instance training-app-db into org group df-og / space group sandbox as user-name...
OK

--- unshare ---
$ cf unshare-service training-app-db -s sandbox
WARNING: Unsharing this service instance will remove any existing bindings originating from the service instance in the space "sandbox". This could cause apps to stop working.

Really unshare the service instance training-app-db from space sandbox? [yN]: y
Unsharing service instance training-app-db from org group df-og / space group sandbox as user-name...
OK
```
- `-o OTHER_ORG_GROUP` is required alongside `-s` when sharing into a space group in a different org group.

## cf create-user-provided-service (cups)
User-provided services can't be shared across spaces.
```
$ cf cups mcp-time-server -p '{"mcpServiceURL":"https://time-mcp-server-quick-mouse-py.apps.example-name.cf-app.com"}'
Creating user provided service mcp-time-server in org group df-og / space group postfacto  as user-name...
OK
```
- `-p` also accepts a comma-separated list of credential key names (`-p "user, password, url"`) to prompt for interactively instead of a JSON blob.