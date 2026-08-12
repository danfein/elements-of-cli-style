# Services

## cf marketplace
```
--- List ---
$ cf marketplace
Getting all service offerings from marketplace in org NAME / space NAME as username...

offering   plans                  description           broker
mysql      small, large, medium   MySQL Database        static-broker
postgres   dev, ha                PostgreSQL Database   static-broker

TIP: Use 'cf marketplace -e SERVICE_OFFERING' to view descriptions of individual plans of a given service offering.

--- Details 1 ---
$ cf marketplace -e mysql 
Getting service plan information for service offering mysql in org student-ssxfh8 / space default as student-ssxfh8...

broker: static-broker
   plan     description     free or paid   costs
   small    Small - 100MB   free           
   large    Large - 10GB    free           
   medium   Medium - 1GB    free   

--- Details 2 ---
$ cf marketplace -e postgres
Getting service plan information for service offering postgres in org student-ssxfh8 / space default as student-ssxfh8...

broker: static-broker
   plan   description                     free or paid   costs
   dev    Development-Mode Unreplicated   free           
   ha     High-Availability Replicated    free        

```
- The “offering” is the name for the service
- Plans are the different “flavours” of the service

## cf service-create
```
 $ cf create-service postgres dev training-app-db
Creating service instance training-app-db in org student-ssxfh8 / space default as student-ssxfh8...

Service instance training-app-db created.
OK
```
- Command feedback takes a few seconds to complete, waiting for acknowledgement.
- The command will not wait for the service to be ready, unless the --wait flag is used.

## cf services
```
$ cf services
Getting service instances in org name-of-org / space space-name as user@company.com...

name   offering         plan       bound apps   last operation     broker           upgrade available
cups   user-provided                            create succeeded
test   app-autoscaler   standard                create succeeded   app-autoscaler   no
```

## cf service
```
$ cf service training-app-db
Showing info of service training-app-db in org student-ssxfh8 / space default as student-ssxfh8...

name:            training-app-db
guid:            67ca4921-5192-48f6-8f8f-86155e74d5a7
type:            managed
broker:          static-broker
offering:        postgres
plan:            dev
tags:            
offering tags:   
description:     PostgreSQL Database
documentation:   
dashboard url:   

Showing status of last operation:
   status:    create succeeded
   message:   
   started:   2025-05-05T20:24:29Z
   updated:   2025-05-05T20:24:29Z

Showing bound apps:
   There are no bound apps for this service instance.

Showing sharing info:
   This service instance is not currently being shared.

Showing upgrade status:
   Upgrades are not supported by this broker.
```

## cf bind-service
```
$ cf bind-service training-app training-app-db
Binding service instance training-app-db to app training-app in org student-ssxfh8 / space default as student-ssxfh8...
OK

TIP: Use 'cf restage training-app' to ensure your env variable changes take effect
```

## cf unbind-service
```
$ cf unbind-service training-app training-app-db
Unbinding app training-app from service training-app-db in org student-ssxfh8 / space default as student-ssxfh8...
OK
```

## cf delete-service
```
$ cf delete-service training-app-db
This action impacts all resources scoped to this service instance, including service bindings, service keys and route bindings.
This will remove the service instance from any spaces where it has been shared.
Really delete the service instance training-app-db? [yN]:
```

## cf create service broker
```
$ cf create-service-broker NAME URL --space-scoped
```
- A service broker is generally created by a platform engineer
- A space developer can create a service broker scoped to a single space. 

## Service Keys
Used to connect directly to a service (on-platform apps are connected automatically)
```
--- Create ---
$ cf create-service-key training-app-db monitoring-creds
Creating service key monitoring-creds for service instance training-app-db as student-ssxfh8...
OK

--- View ---
 $ cf service-key training-app-db monitoring-creds
Getting key monitoring-creds for service instance training-app-db as student-ssxfh8...

{
  "credentials": {
    "hostname": "postgresql.example.com",
    "jdbcUrl": "jdbc:postgresql://user:Password@postgresql.example.com:5430/dev_db?ssl=true&loglevel=2",
    "name": "dev_db",
    "password": "Password",
    "uri": "postgresql://user:Password@postgresql.example.com:5430/dev_db",
    "username": "user"
  }
}

```

## cf service offerings
```
$ cf curl /v3/service_offerings | jq
{
  "pagination": {
    "total_results": 2,
    "total_pages": 1,
    "first": {
      "href": "https://api.sys.zone-3924730.cf-app.com/v3/service_offerings?page=1&per_page=50"
    },
    "last": {
      "href": "https://api.sys.zone-3924730.cf-app.com/v3/service_offerings?page=1&per_page=50"
    },
    "next": null,
    "previous": null
  },
  "resources": [
    {
      "guid": "b51c415f-6ada-4d32-b568-e8579b8e5b98",
      "created_at": "2025-05-04T05:32:30Z",
      "updated_at": "2025-05-04T05:32:30Z",
      "name": "mysql",
      "description": "MySQL Database",
      "available": true,
      "tags": [],
      "requires": [],
      "shareable": true,
      "documentation_url": "",
      "broker_catalog": {
        "id": "mysql",
        "metadata": {
          "longDescription": "MySQL database instances of different sizes",
          "shareable": true,
          "documentationUrl": "",
          "providerDisplayName": "",
          "displayName": "mysql",
          "imageUrl": "",
          "supportUrl": ""
        },
        "features": {
          "plan_updateable": true,
          "bindable": true,
          "instances_retrievable": false,
          "bindings_retrievable": false,
          "allow_context_updates": false
        }
      },
      "relationships": {
        "service_broker": {
          "data": {
            "guid": "e04c37a0-d0bf-4607-9cdf-2dd110fc3ed3"
          }
        }
      },
      "metadata": {
        "labels": {},
        "annotations": {}
      },
      "links": {
        "self": {
          "href": "https://api.sys.zone-3924730.cf-app.com/v3/service_offerings/b51c415f-6ada-4d32-b568-e8579b8e5b98"
        },
        "service_plans": {
          "href": "https://api.sys.zone-3924730.cf-app.com/v3/service_plans?service_offering_guids=b51c415f-6ada-4d32-b568-e8579b8e5b98"
        },
        "service_broker": {
          "href": "https://api.sys.zone-3924730.cf-app.com/v3/service_brokers/e04c37a0-d0bf-4607-9cdf-2dd110fc3ed3"
        }
      }
    },
    {
      "guid": "0c1dc10e-b9b9-4b20-a0b8-f2d6814aa855",
      "created_at": "2025-05-04T05:32:30Z",
      "updated_at": "2025-05-04T05:32:30Z",
      "name": "postgres",
      "description": "PostgreSQL Database",
      "available": true,
      "tags": [],
      "requires": [],
      "shareable": true,
      "documentation_url": "",
      "broker_catalog": {
        "id": "postgres",
        "metadata": {
          "longDescription": "PostgreSQL database instances of different sizes",
          "shareable": true,
          "documentationUrl": "",
          "providerDisplayName": "",
          "displayName": "postgres",
          "imageUrl": "",
          "supportUrl": ""
        },
        "features": {
          "plan_updateable": true,
          "bindable": true,
          "instances_retrievable": false,
          "bindings_retrievable": false,
          "allow_context_updates": false
        }
      },
      "relationships": {
        "service_broker": {
          "data": {
            "guid": "e04c37a0-d0bf-4607-9cdf-2dd110fc3ed3"
          }
        }
      },
      "metadata": {
        "labels": {},
        "annotations": {}
      },
      "links": {
        "self": {
          "href": "https://api.sys.zone-3924730.cf-app.com/v3/service_offerings/0c1dc10e-b9b9-4b20-a0b8-f2d6814aa855"
        },
        "service_plans": {
          "href": "https://api.sys.zone-3924730.cf-app.com/v3/service_plans?service_offering_guids=0c1dc10e-b9b9-4b20-a0b8-f2d6814aa855"
        },
        "service_broker": {
          "href": "https://api.sys.zone-3924730.cf-app.com/v3/service_brokers/e04c37a0-d0bf-4607-9cdf-2dd110fc3ed3"
        }
      }
    }
  ]
}
```


## Sharable Services
Service sharing across spaces needs to be enabled globally by a platform admin
A shared service cannot be renamed or updated
Deleting the service from any space it is shared in deletes it everywhere
```
--- share service ---
$ cf share-service training-app-db -s services
Sharing service instance training-app-db into org student-ssxfh8 / space services as student-ssxfh8...
OK

--- unshare service ---
cf unshare-service training-app-db -s services
WARNING: Unsharing this service instance will remove any existing bindings originating from the service instance in the space "services". This could cause apps to stop working.

Really unshare the service instance training-app-db from space services? [yN]: 
Unsharing service instance training-app-db from org student-ssxfh8 / space services as student-ssxfh8...
OK
```
- Note, a service is shared from the space it was created in
- Insecting a shared service will only show bound apps for the space it is in

## User created servces 
Cannot be shared across spaces
```
--- Create from file ---
$ cf create-user-provided-service 
// or
$ cf cups NAME -p cups.json
Creating user provided service non-interactive in org student-ssxfh8 / space services as student-ssxfh8...
OK

--- Create interactively ---
$ cf cups NAME -p "user, password, url"
user: 
password: 
url: 
Creating user provided service interactive in org student-ssxfh8 / space services as student-ssxfh8...
OK
```

## service backup list
```
$ cf service-backups -h
NAME:
   service-backups - List backups for a service instance

USAGE:
   cf service-backups SERVICE_INSTANCE [-l NUM]

OPTIONS:
   --limit, -l       Number of recent backups to display (Default: 5)
   --fg              Foundation group name (Tanzu Hub only)
   --foundation      Foundation name (Tanzu Hub only)

SEE ALSO:
   create-service-backup, restore-service-backup
---
cf service-backups postfacto-redis
Getting backups of service instance postfacto-redis in org df-og / space postfacto as tanzu_platform_admin...

Backup ID                                         Name   Time of Backup
4a3e7513-70a3-4610-a488-3c6a285eec73_1786554072          Wed Aug 12 17:01:12 UTC 2026

```

## Sevice backup
```
cf create-service-backup -h
NAME:
   create-service-backup - Create a backup of a service instance

USAGE:
   cf create-service-backup SERVICE_INSTANCE [-n NAME] [-w]

OPTIONS:
   --name, -n        Optional name for the backup
   --wait, -w        Wait for the operation to complete
   --fg              Foundation group name (Tanzu Hub only)
   --foundation      Foundation name (Tanzu Hub only)

SEE ALSO:
   restore-service-backup, service-backups
---
$ cf create-service-backup postfacto-redis
Creating backup of service instance postfacto-redis in org df-og / space postfacto as tanzu_platform_admin...

Backup creation initiated for service instance postfacto-redis.

Job GUID: c400b971-8a7d-4cde-8c79-48558d40d54c
Check job status with: cf curl /v3/jobs/c400b971-8a7d-4cde-8c79-48558d40d54c
```

## Restore service backup
```
$ cf restore-service-backup -h
NAME:
   restore-service-backup - Restore a service instance from a backup

USAGE:
   cf restore-service-backup SERVICE_INSTANCE [--backup-id ID] [--target-timestamp TIME] [--restore-point TYPE] [--source-service-instance-guid GUID] [-f] [-w]

OPTIONS:
   --backup-id                         ID of the backup to restore from
   --target-timestamp                  Point-in-time to restore to
   --restore-point                     Restore type: full-only, latest, or point-in-time
   --source-service-instance-guid      GUID of the source service instance for cross-instance restore
   --force, -f                         Force restore without confirmation
   --wait, -w                          Wait for the operation to complete
   --fg                                Foundation group name (Tanzu Hub only)
   --foundation                        Foundation name (Tanzu Hub only)

---

$ cf restore-service-backup postfacto-redis --backup-id 4a3e7513-70a3-4610-a488-3c6a285eec73_1786554072
Restoring service instance postfacto-redis in org df-og / space postfacto as tanzu_platform_admin...
This action will overwrite all data in this service instance.
Really restore the service instance postfacto-redis? [yN]: y

Restore initiated for service instance postfacto-redis.

Job GUID: 4ba029ff-87a6-45a3-a4b9-eac6f7116e01
Check job status with: cf curl /v3/jobs/4ba029ff-87a6-45a3-a4b9-eac6f7116e01
OK
```