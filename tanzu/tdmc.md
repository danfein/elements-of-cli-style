# Tanzu Data Managment Console (TDMC)

## Help
```
*************************************************
Welcome to Tanzu Data Management Console CLI
*************************************************
This CLI supports all the service operations provided by Tanzu Data Management Console.
Currently Tanzu Data provides RabbitMQ, Postgres, Mysql and Valkey as service offerings.

Example usage flow:
``
    Create a profile and configure against a TDMC instance
  $ tdmc profile create
  $ tdmc configure

  # Propagate the password for the profile
  $ export TDMC_PASSWORD='PASSWORD_FOR_PROFILE'

  # Example command
  $ tdmc sre data-plane list
``

Usage:
  tdmc [flags]
  tdmc [command]

Available Commands:
  completion   Generate the autocompletion script for the specified shell
  configure    Configure Default Options for CLI
  dev          Perform operations on the environment.
  help         Help about any command
  iam          Perform Identity and Access Management Operations
  mysql        To Perform Operations for MySQL Cluster
  object-store To Perform Operations for Object Store
  postgres     To Perform Operations for Postgres Cluster
  profile      To Create/Update/Delete a profile.
  rmq          To Perform Operations for RabbitMQ Cluster
  sre          Perform SRE Related Operations
  task         Perform Task Related Operations
  valkey       To Perform Operations for Valkey Cluster

Flags:
  -h, --help                  help for tdmc
      --page int              Specify page number (default 0)
      --profile-name string   Profile to use
      --size int              Specify page size (default 1000)
  -v, --version               version for tdmc

Use "tdmc [command] --help" for more information about a command.
```

## Getting Started
```

--- profile create ---
$ tdmc profile create
Enter Profile Name (cannot be blank) - dftest
Enter email: user.name@company,com
Enter OrgId (cannot be blank) - 99dd3967-aabb-4481-0000-362e6e6c3255
Profile Added with name -  dftest

--- tdmc profile list ---
$ tdmc profile list
[
    "dftest"
]

--- tdmc profile get ---
$tdmc profile get dftest
Enter Profile Name (cannot be blank) - dftest
{
    "Name": "dftest",
    "CredentialsType": "user_creds",
    "Username": "user.name@company,com",
    "Org": "99dd3967-aabb-4481-0000-362e6e6c3255"
}


--- configure ---
$tdmc configure
Enter Endpoint URL - []: https://tdmc-cp-pve.tdmc.pve.acc.company.net/
Enter Profile name - []: dftest

--- Auth failure ---
$ tdmc sre data-plane list
Method: GET || URL: https://tdmc-cp-pve.tdmc.pve.acc.company.net/api/infra-connector/internal/k8s-cluster?size=1000 || Status Code: 403 || Message: Access is denied
: HTTP_REQ_EXECUTION_ERROR
{
    "status": 403,
    "errorMsg": "Access is denied",
    "errorCode": "ACCESS_DENIED"
}
```
## TDMC Postgres
```
--- help ---
$ tdmc postgres
To Perform Operations for Postgres Cluster

Usage:
  tdmc postgres [flags]
  tdmc postgres [command]

Available Commands:
  attach-network-policy To Attach The Given Network Policy to Postgres Cluster
  backup                To perform backup of Postgres Cluster
  create                To Create Postgres Cluster
  delete                To Delete A Postgres Cluster
  dr                    To perform operations related to disaster recovery (DR)
  list                  To List Postgres Cluster Instance/s
  restore               To perform restore of Postgres Cluster
  update                To Update the tags for the Postgres Cluster
  upgrade               To upgrade postgres Cluster to next Target version

Flags:
  -h, --help   help for postgres

Global Flags:
      --page int              Specify page number (default 0)
      --profile-name string   Profile to use
      --size int              Specify page size (default 1000)

Use "tdmc postgres [command] --help" for more information about a command.

--- list ---
tdmc postgres list
[
    {
        "id": "1fdfa221-e21d-4015-aaaa-824763c66e56",
        "name": "dr-df-pgtest",
        "status": "PROVISIONING",
        "serviceType": "POSTGRES",
        "tags": [
            "test"
        ],
        "instanceSize": "X-SMALL",
        "provider": "tkgs",
        "dataPlaneId": "b93223e0-355b-aaaa-a9ab-1139db3378a5",
        "version": "postgres-17",
        "region": "tanzu",
        "metadata": {
            "metricsEnpoints": null,
            "connectionUri": ""
        }
    },
    {
        "id": "6c970d13-0873-486c-aaaa-04b55ca9f5e3",
        "name": "df-pgtest",
        "status": "READY",
        "serviceType": "POSTGRES",
        "tags": [
            "test"
        ],
        "instanceSize": "X-SMALL",
        "provider": "tkgs",
        "dataPlaneId": "7594feba-a42e-4b0c-aaaa-1cdd6e9b26f2",
        "version": "postgres-17",
        "region": "tanzu",
        "metadata": {
            "metricsEnpoints": [
                "https://df-pgtest-n2zjodjizt-tanzu.tdmc.pve.acc.company.net/metrics"
            ],
            "connectionUri": "postgres://{user}:{password}@df-pgtest-n2zjodjizt-tanzu.tdmc.pve.acc.company.net:5432/{databasename}"
        }
    }
]
```

## TDMC DR
```
--- help ---
$ tdmc postgres dr
To perform operations related to disaster recovery (DR)

Usage:
  tdmc postgres dr [command]

Available Commands:
  create       To create a disaster recovery instance
  delete       To delete the disaster recovery instance if it exists
  fail-over    To fail-over a postgres cluster
  list         To list the disaster recovery instance if it exists
  relink-as-dr Trigger a task that will demote a primary to a DR and link it to the other primary.

Flags:
  -h, --help   help for dr

Global Flags:
      --page int              Specify page number (default 0)
      --profile-name string   Profile to use
      --size int              Specify page size (default 1000)

Use "tdmc postgres dr [command] --help" for more information about a command.


--- list ---
$ tdmc postgres dr list
null
```