# cf cli

Styleguide
```
https://github.com/cloudfoundry/cli/wiki/CF-CLI-Style-Guide
```


Install
```
$ brew install cloudfoundry/tap/cf-cli@8
```

Help - short
```
$ cf --help

cf version 8.14.1+2bcb856.2025-06-10, Cloud Foundry command line tool
Usage: cf [global options] command [arguments...] [command options]

Before getting started:
  config    login,l      target,t
  help,h    logout,lo

Application lifecycle:
  apps,a        run-task,rt    events
  push,p        logs           set-env,se
  start,st      ssh            create-app-manifest
  stop,sp       app            delete,d
  restart,rs    env,e          apply-manifest
  restage,rg    scale          revisions

Services integration:
  marketplace,m        create-user-provided-service,cups
  services,s           update-user-provided-service,uups
  create-service,cs    create-service-key,csk
  update-service       delete-service-key,dsk
  delete-service,ds    service-keys,sk
  service              service-key
  bind-service,bs      bind-route-service,brs
  unbind-service,us    unbind-route-service,urs

Route and domain management:
  routes,r        delete-route    create-private-domain,create-domain
  domains         map-route
  create-route    unmap-route

Space management:
  spaces            create-space,csp    set-space-role
  space-users       delete-space        unset-space-role
  apply-manifest

Org management:
  orgs,o       set-org-role
  org-users    unset-org-role

CLI plugin management:
  plugins           add-plugin-repo      repo-plugins
  install-plugin    list-plugin-repos

Commands offered by installed plugins:

Global options:
  --help, -h                         Show help
  -v                                 Print API request diagnostics to stdout

TIP: Use 'cf help -a' to see all commands.
```

Help full
```
$ cf --help -a

NAME:
   cf - A command line tool to interact with Cloud Foundry

USAGE:
   cf [global options] command [arguments...] [command options]

VERSION:
   8.14.1+2bcb856.2025-06-10

GETTING STARTED:
   help                                   Show help
   version                                Print the version
   login                                  Log user in
   logout                                 Log user out
   passwd                                 Change user password
   target                                 Set or view the targeted org or space

   api                                    Set or view target api url
   auth                                   Authenticate non-interactively

APPS:
   apps                                   List all apps in the target space
   app                                    Display health and status for an app
   create-app                             Create an Application in the target space

   push                                   Push a new app or sync changes to an existing app
   scale                                  Change or view the instance count, disk space limit, memory limit, and log rate limit for an app
   delete                                 Delete an app
   rename                                 Rename an app

   cancel-deployment                      Cancel the most recent deployment for an app. Resets the current droplet to the previous deployment's droplet.
   continue-deployment                    Continue the most recent deployment for an app.

   start                                  Start an app
   stop                                   Stop an app
   restart                                Stop all instances of the app, then start them again.
   stage-package                          Stage a package into a droplet
   restage                                Stage the app's latest package into a droplet and restart the app with this new droplet and updated configuration (environment variables, service bindings, buildpack, stack, etc.).
   restart-app-instance                   Stop, then start application instance without updating application environment

   run-task                               Run a one-off task on an app
   task                                   Display a task of an app
   tasks                                  List tasks of an app
   terminate-task                         Terminate a running task of an app

   packages                               List packages of an app
   create-package                         Uploads a Package

   revision                               Show details for a specific app revision
   revisions                              List revisions of an app
   rollback                               Rollback to the specified revision of an app

   droplets                               List droplets of an app
   set-droplet                            Set the droplet used to run an app
   download-droplet                       Download an application droplet

   events                                 Show recent app events
   logs                                   Tail or show recent logs for an app

   env                                    Show all env variables for an app
   set-env                                Set an env variable for an app
   unset-env                              Remove an env variable from an app

   stacks                                 List all stacks (a stack is a pre-built file system, including an operating system, that can run apps)
   stack                                  Show information for a stack (a stack is a pre-built file system, including an operating system, that can run apps)

   copy-source                            Copies the source code of an application to another existing application and restages that application
   create-app-manifest                    Create an app manifest for an app that has been pushed successfully

   get-health-check                       Show the type of health check performed on an app
   set-health-check                       Change type of health check performed on an app's process
   get-readiness-health-check             Show the type of readiness health check performed on an app

   enable-ssh                             Enable ssh for the application
   disable-ssh                            Disable ssh for the application
   ssh-enabled                            Reports whether SSH is enabled on an application container instance
   ssh                                    SSH to an application container instance

SERVICES:
   marketplace                            List available offerings in the marketplace
   services                               List all service instances in the target space
   service                                Show service instance info

   create-service                         Create a service instance
   update-service                         Update a service instance
   upgrade-service                        Upgrade a service instance to the latest available version of its current service plan
   delete-service                         Delete a service instance
   rename-service                         Rename a service instance

   create-service-key                     Create key for a service instance
   service-keys                           List keys for a service instance
   service-key                            Show service key info
   delete-service-key                     Delete a service key

   bind-service                           Bind a service instance to an app
   unbind-service                         Unbind a service instance from an app

   bind-route-service                     Bind a service instance to an HTTP route
   unbind-route-service                   Unbind a service instance from an HTTP route

   create-user-provided-service           Make a user-provided service instance available to CF apps
   update-user-provided-service           Update user-provided service instance

   share-service                          Share a service instance with another space
   unshare-service                        Unshare a shared service instance from a space

ORGS:
   orgs                                   List all orgs
   org                                    Show org info

   create-org                             Create an org
   delete-org                             Delete an org
   rename-org                             Rename an org

SPACES:
   spaces                                 List all spaces in an org
   space                                  Show space info

   create-space                           Create a space
   delete-space                           Delete a space
   rename-space                           Rename a space
   apply-manifest                         Apply manifest properties to a space

   allow-space-ssh                        Allow SSH access for the space
   disallow-space-ssh                     Disallow SSH access for the space
   space-ssh-allowed                      Reports whether SSH is allowed in a space

DOMAINS:
   domains                                List domains in the target org

   create-private-domain                  Create a private domain for a specific org
   delete-private-domain                  Delete a private domain

   create-shared-domain                   Create a domain that can be used by all orgs (admin-only)
   delete-shared-domain                   Delete a shared domain

   router-groups                          List router groups

ROUTES:
   routes                                 List all routes in the current space or the current organization
   route                                  Display route details and mapped destinations

   create-route                           Create a route for later use
   update-route                           Update a route by route specific options, e.g. load balancing algorithm
   check-route                            Perform a check to determine whether a route currently exists or not
   map-route                              Map a route to an app
   unmap-route                            Remove a route from an app
   delete-route                           Delete a route

   delete-orphaned-routes                 Delete all orphaned routes in the currently targeted space (i.e. those that are not mapped to an app or service instance)

   update-destination                     Updates the destination protocol for a route

   share-route                            Share a route in between spaces
   unshare-route                          Unshare an existing route from a space

   move-route                             Assign a route to a different space

NETWORK POLICIES:
   network-policies                       List direct network traffic policies
   add-network-policy                     Create policy to allow direct network traffic from one app to another
   remove-network-policy                  Remove network traffic policy of an app

BUILDPACKS:
   buildpacks                             List all buildpacks
   create-buildpack                       Create a buildpack
   update-buildpack                       Update a buildpack

   delete-buildpack                       Delete a buildpack

USER ADMIN:
   create-user                            Create a new user
   delete-user                            Delete a user

   org-users                              Show org users by role
   set-org-role                           Assign an org role to a user
   unset-org-role                         Remove an org role from a user

   space-users                            Show space users by role
   set-space-role                         Assign a space role to a user
   unset-space-role                       Remove a space role from a user

ORG ADMIN:
   org-quotas                             List available organization quotas
   org-quota                              Show organization quota
   set-org-quota                          Assign a quota to an organization

   create-org-quota                       Define a new quota for an organization
   delete-org-quota                       Delete an organization quota
   update-org-quota                       Update an existing organization quota

   share-private-domain                   Share a private domain with a specific org
   unshare-private-domain                 Unshare a private domain with a specific org

SPACE ADMIN:
   space-quotas                           List available space quotas
   space-quota                            Show space quota info

   create-space-quota                     Define a new quota for a space
   update-space-quota                     Update an existing space quota
   delete-space-quota                     Delete a space quota

   set-space-quota                        Assign a quota to a space
   unset-space-quota                      Unassign a quota from a space

SERVICE ADMIN:
   service-brokers                        List service brokers
   create-service-broker                  Create a service broker
   update-service-broker                  Update a service broker
   delete-service-broker                  Delete a service broker
   rename-service-broker                  Rename a service broker

   purge-service-offering                 Recursively remove a service offering and child objects from Cloud Foundry database without making requests to a service broker
   purge-service-instance                 Recursively remove a service instance and child objects from Cloud Foundry database without making requests to a service broker

   service-access                         List service access settings
   enable-service-access                  Enable access to a service offering or service plan for one or all orgs
   disable-service-access                 Disable access to a service offering or service plan for one or all orgs

SECURITY GROUP:
   security-group                         Show a single security group
   security-groups                        List all security groups
   create-security-group                  Create a security group
   update-security-group                  Update a security group
   delete-security-group                  Deletes a security group
   bind-security-group                    Bind a security group to a particular space, or all existing spaces of an org
   unbind-security-group                  Unbind a security group from a space

   bind-staging-security-group            Bind a security group to the list of security groups to be used for staging applications globally
   staging-security-groups                List security groups globally configured for staging applications
   unbind-staging-security-group          Unbind a security group from the set of security groups for staging applications globally

   bind-running-security-group            Bind a security group to the list of security groups to be used for running applications
   running-security-groups                List security groups globally configured for running applications
   unbind-running-security-group          Unbind a security group from the set of security groups for running applications globally

ENVIRONMENT VARIABLE GROUPS:
   running-environment-variable-group     Retrieve the contents of the running environment variable group
   staging-environment-variable-group     Retrieve the contents of the staging environment variable group
   set-staging-environment-variable-group Pass parameters as JSON to create a staging environment variable group
   set-running-environment-variable-group Pass parameters as JSON to create a running environment variable group

ISOLATION SEGMENTS:
   isolation-segments                     List all isolation segments
   create-isolation-segment               Create an isolation segment
   delete-isolation-segment               Delete an isolation segment
   enable-org-isolation                   Entitle an organization to an isolation segment
   disable-org-isolation                  Revoke an organization's entitlement to an isolation segment
   set-org-default-isolation-segment      Set the default isolation segment used for apps in spaces in an org
   reset-org-default-isolation-segment    Reset the default isolation segment used for apps in spaces of an org
   set-space-isolation-segment            Assign the isolation segment for a space
   reset-space-isolation-segment          Reset the space's isolation segment to the org default

FEATURE FLAGS:
   feature-flags                          Retrieve list of feature flags with status
   feature-flag                           Retrieve an individual feature flag with status
   enable-feature-flag                    Allow use of a feature
   disable-feature-flag                   Prevent use of a feature

METADATA:
   labels                                 List all labels (key-value pairs) for an API resource
   set-label                              Set a label (key-value pairs) for an API resource
   unset-label                            Unset a label (key-value pairs) for an API resource

ADVANCED:
   curl                                   Executes a request to the targeted API endpoint
   config                                 Write default values to the config
   oauth-token                            Display the OAuth token for the current session and refresh the token if necessary
   ssh-code                               Get a one time password for ssh clients

ADD/REMOVE PLUGIN REPOSITORY:
   add-plugin-repo                        Add a new plugin repository
   remove-plugin-repo                     Remove a plugin repository
   list-plugin-repos                      List all the added plugin repositories
   repo-plugins                           List all available plugins in specified repository or in all added repositories

ADD/REMOVE PLUGIN:
   plugins                                List commands of installed plugins
   install-plugin                         Install CLI plugin
   uninstall-plugin                       Uninstall CLI plugin

INSTALLED PLUGIN COMMANDS:

ENVIRONMENT VARIABLES:
   CF_COLOR=false                     Do not colorize output
   CF_DIAL_TIMEOUT=6                  Max wait time to establish a connection, including name resolution, in seconds
   CF_HOME=path/to/dir/               Override path to default config directory
   CF_PLUGIN_HOME=path/to/dir/        Override path to default plugin config directory
   CF_TRACE=true                      Print API request diagnostics to stdout
   CF_TRACE=path/to/trace.log         Append API request diagnostics to a log file
   all_proxy=proxy.example.com:8080   Specify a proxy server to enable proxying for all requests
   https_proxy=proxy.example.com:8080 Enable proxying for HTTP requests

GLOBAL OPTIONS:
   --help, -h                         Show help
   -v                                 Print API request diagnostics to stdout

```