# Help Text

## Pihole (dns adblocker)

```
Usage: pihole [options]
Example: 'pihole -w -h'
Add '-h' after specific commands for more information on usage

Whitelist/Blacklist Options:
  -w, whitelist       Whitelist domain(s)
  -b, blacklist       Blacklist domain(s)
  --regex, regex      Regex blacklist domains(s)
  --white-regex       Regex whitelist domains(s)
  --wild, wildcard    Wildcard blacklist domain(s)
  --white-wild        Wildcard whitelist domain(s)
                        Add '-h' for more info on whitelist/blacklist usage

Debugging Options:
  -d, debug           Start a debugging session
                        Add '-a' to automatically upload the log to tricorder.pi-hole.net
  -f, flush           Flush the Pi-hole log
  -r, reconfigure     Reconfigure or Repair Pi-hole subsystems
  -t, tail [arg]      View the live output of the Pi-hole log.
                      Add an optional argument to filter the log
                      (regular expressions are supported)


Options:
  -a, admin           Web interface options
                        Add '-h' for more info on Web Interface usage
  -c, chronometer     Calculates stats and displays to an LCD
                        Add '-h' for more info on chronometer usage
  -g, updateGravity   Update the list of ad-serving domains
  -h, --help, help    Show this help dialog
  -l, logging         Specify whether the Pi-hole log should be used
                        Add '-h' for more info on logging usage
  -q, query           Query the adlists for a specified domain
                        Add '-h' for more info on query usage
  -up, updatePihole   Update Pi-hole subsystems
                        Add '--check-only' to exit script before update is performed.
  -v, version         Show installed versions of Pi-hole, Web Interface & FTL
                        Add '-h' for more info on version usage
  uninstall           Uninstall Pi-hole from your system
  status              Display the running status of Pi-hole subsystems
  enable              Enable Pi-hole subsystems
  disable             Disable Pi-hole subsystems
                        Add '-h' for more info on disable usage
  restartdns          Full restart Pi-hole subsystems
                        Add 'reload' to update the lists and flush the cache without restarting the DNS server
                        Add 'reload-lists' to only update the lists WITHOUT flushing the cache or restarting the DNS server
  checkout            Switch Pi-hole subsystems to a different GitHub branch
                        Add '-h' for more info on checkout usage
  arpflush            Flush information stored in Pi-hole's network tables
```

Grouped by functions
Flags use a mix of single and double dashes

## OpsManager OM CLI

```
➜  ~ om
Usage:
  om [OPTIONS] <command>

Application Options:
      --ca-cert=               OpsManager CA certificate path or value [$OM_CA_CERT]
  -c, --client-id=             Client ID for the Ops Manager VM (not required for unauthenticated commands)
                               [$OM_CLIENT_ID]
  -s, --client-secret=         Client Secret for the Ops Manager VM (not required for unauthenticated commands)
                               [$OM_CLIENT_SECRET]
  -o, --connect-timeout=       timeout in seconds to make TCP connections (default: 10) [$OM_CONNECT_TIMEOUT]
  -d, --decryption-passphrase= Passphrase to decrypt the installation if the Ops Manager VM has been rebooted
                               (optional for most commands) [$OM_DECRYPTION_PASSPHRASE]
  -e, --env=                   env file with login credentials
  -p, --password=              admin password for the Ops Manager VM (not required for unauthenticated commands)
                               [$OM_PASSWORD]
  -r, --request-timeout=       timeout in seconds for HTTP requests to Ops Manager (default: 1800)
                               [$OM_REQUEST_TIMEOUT]
  -k, --skip-ssl-validation    skip ssl certificate validation during http requests [$OM_SKIP_SSL_VALIDATION]
  -t, --target=                location of the Ops Manager VM [$OM_TARGET]
      --uaa-target=            optional location of the Ops Manager UAA [$OM_UAA_TARGET]
      --trace                  prints HTTP requests and response payloads [$OM_TRACE]
  -u, --username=              admin username for the Ops Manager VM (not required for unauthenticated commands)
                               [$OM_USERNAME]
      --vars-env=              load vars from environment variables by specifying a prefix (e.g.: 'MY' to load
                               MY_var=value) [$OM_VARS_ENV]
  -v, --version                prints the om release version

Help Options:
  -h, --help                   Show this help message

Available commands:
  activate-certificate-authority  activates a certificate authority on the Ops Manager
  apply-changes                   triggers an install on the Ops Manager targeted
  assign-multi-stemcell           assigns multiple uploaded stemcells to a product in the targeted Ops Manager 2.6+
  assign-stemcell                 assigns an uploaded stemcell to a product in the targeted Ops Manager
  available-products              **DEPRECATED** lists available products. Use 'products --available' instead.
  bosh-diff                       displays BOSH manifest diff for the director and products
  bosh-env                        prints environment variables for BOSH and Credhub
  certificate-authorities         lists certificates managed by Ops Manager
  certificate-authority           prints requested certificate authority
  config-template                 generates a config template from a Pivnet product
  configure-authentication        configures Ops Manager with an internal userstore and admin user account
  configure-director              configures the director
  configure-ldap-authentication   configures Ops Manager with LDAP authentication
  configure-opsman                configures values present on the Ops Manager settings page
  configure-product               configures a staged product
  configure-saml-authentication   configures Ops Manager with SAML authentication
  create-certificate-authority    creates a certificate authority on the Ops Manager
  create-vm-extension             creates/updates a VM extension
  credential-references           list credential references for a deployed product
  credentials                     fetch credentials for a deployed product
  curl                            issues an authenticated API request
  delete-certificate-authority    deletes a certificate authority on the Ops Manager
  delete-installation             deletes all the products on the Ops Manager targeted
  delete-product                  deletes an unused product from the Ops Manager
  delete-ssl-certificate          deletes certificate applied to Ops Manager
  delete-unused-products          deletes unused products on the Ops Manager targeted
  deployed-manifest               prints the deployed manifest for a product
  deployed-products               **DEPRECATED** lists deployed products. Use 'products --deployed' instead.
  diagnostic-report               reports current state of your Ops Manager
  disable-director-verifiers      disables director verifiers
  disable-product-verifiers       disables product verifiers
  download-product                downloads a specified product file from Pivotal Network
  errands                         list errands for a product
  expiring-certificates           lists expiring certificates from the Ops Manager targeted
  export-installation             exports the installation of the target Ops Manager
  generate-certificate            generates a new certificate signed by Ops Manager's root CA
  generate-certificate-authority  generates a certificate authority on the Opsman
  import-installation             imports a given installation to the Ops Manager targeted
  installation-log                output installation logs
  installations                   list recent installation events
  interpolate                     interpolates variables into a manifest
  pending-changes                 checks for pending changes
  pre-deploy-check                checks completeness and validity of product configuration
  product-metadata                prints product metadata
  products                        lists product staged, available, and deployed versions
  regenerate-certificates         deletes all non-configurable certificates in Ops Manager so they will automatically be regenerated on the next apply-changes
  revert-staged-changes           This command reverts the staged changes already on an Ops Manager.
  ssl-certificate                 gets certificate applied to Ops Manager
  stage-product                   stages a given product in the Ops Manager targeted
  staged-config                   generates a config from a staged product
  staged-director-config          generates a config from a staged director
  staged-manifest                 prints the staged manifest for a product
  staged-products                 **DEPRECATED** lists staged products. Use 'products --staged' instead.
  unstage-product                 unstages a given product from the Ops Manager targeted
  upload-product                  uploads a given product to the Ops Manager targeted
  upload-stemcell                 uploads a given stemcell to the Ops Manager targeted
  version                         prints the om release version
  vm-lifecycle                    commands to manage the state of the Ops Manager VM (aliases: nom)

```

## CF CLI
```
➜  ~ cf
cf version 8.12.0+636312f.2025-03-28, Cloud Foundry command line tool
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
```


## Openshift OC CLI

```
➜  ~ oc
OpenShift Client

This client helps you develop, build, deploy, and run your applications on any
OpenShift or Kubernetes cluster. It also includes the administrative
commands for managing a cluster under the 'adm' subcommand.

Basic Commands:
  login             Log in to a server
  new-project       Request a new project
  new-app           Create a new application
  status            Show an overview of the current project
  project           Switch to another project
  projects          Display existing projects
  explain           Get documentation for a resource

Build and Deploy Commands:
  rollout           Manage a Kubernetes deployment or OpenShift deployment config
  rollback          Revert part of an application back to a previous deployment
  new-build         Create a new build configuration
  start-build       Start a new build
  cancel-build      Cancel running, pending, or new builds
  import-image      Import images from a container image registry
  tag               Tag existing images into image streams

Application Management Commands:
  create            Create a resource from a file or from stdin
  apply             Apply a configuration to a resource by file name or stdin
  get               Display one or many resources
  describe          Show details of a specific resource or group of resources
  edit              Edit a resource on the server
  set               Commands that help set specific features on objects
  label             Update the labels on a resource
  annotate          Update the annotations on a resource
  expose            Expose a replicated application as a service or route
  delete            Delete resources by file names, stdin, resources and names, or by resources and
label selector
  scale             Set a new size for a deployment, replica set, or replication controller
  autoscale         Autoscale a deployment config, deployment, replica set, stateful set, or
replication controller
  secrets           Manage secrets

Troubleshooting and Debugging Commands:
  logs              Print the logs for a container in a pod
  rsh               Start a shell session in a container
  rsync             Copy files between a local file system and a pod
  port-forward      Forward one or more local ports to a pod
  debug             Launch a new instance of a pod for debugging
  exec              Execute a command in a container
  proxy             Run a proxy to the Kubernetes API server
  attach            Attach to a running container
  run               Run a particular image on the cluster
  cp                Copy files and directories to and from containers
  wait              Experimental: Wait for a specific condition on one or many resources
  events            List events

Advanced Commands:
  adm               Tools for managing a cluster
  replace           Replace a resource by file name or stdin
  patch             Update fields of a resource
  process           Process a template into list of resources
  extract           Extract secrets or config maps to disk
  observe           Observe changes to resources and react to them (experimental)
  policy            Manage authorization policy
  auth              Inspect authorization
  image             Useful commands for managing images
  registry          Commands for working with the registry
  idle              Idle scalable resources
  api-versions      Print the supported API versions on the server, in the form of "group/version"
  api-resources     Print the supported API resources on the server
  cluster-info      Display cluster information
  diff              Diff the live version against a would-be applied version
  kustomize         Build a kustomization target from a directory or URL

Settings Commands:
  get-token         Experimental: Get token from external OIDC issuer as credentials exec plugin
  logout            End the current server session
  config            Modify kubeconfig files
  whoami            Return information about the current session
  completion        Output shell completion code for the specified shell (bash, zsh, fish, or
powershell)

Other Commands:
  plugin            Provides utilities for interacting with plugins
  version           Print the client and server version information

Usage:
  oc [flags] [options]

Use "oc <command> --help" for more information about a given command.
Use "oc options" for a list of global command-line options (applies to all commands).
```
## Kubectl

```
➜  ~ kubectl
kubectl controls the Kubernetes cluster manager.

 Find more information at: https://kubernetes.io/docs/reference/kubectl/

Basic Commands (Beginner):
  create          Create a resource from a file or from stdin
  expose          Take a replication controller, service, deployment or pod and expose it as a new
Kubernetes service
  run             Run a particular image on the cluster
  set             Set specific features on objects

Basic Commands (Intermediate):
  explain         Get documentation for a resource
  get             Display one or many resources
  edit            Edit a resource on the server
  delete          Delete resources by file names, stdin, resources and names, or by resources and
label selector

Deploy Commands:
  rollout         Manage the rollout of a resource
  scale           Set a new size for a deployment, replica set, or replication controller
  autoscale       Auto-scale a deployment, replica set, stateful set, or replication controller

Cluster Management Commands:
  certificate     Modify certificate resources
  cluster-info    Display cluster information
  top             Display resource (CPU/memory) usage
  cordon          Mark node as unschedulable
  uncordon        Mark node as schedulable
  drain           Drain node in preparation for maintenance
  taint           Update the taints on one or more nodes

Troubleshooting and Debugging Commands:
  describe        Show details of a specific resource or group of resources
  logs            Print the logs for a container in a pod
  attach          Attach to a running container
  exec            Execute a command in a container
  port-forward    Forward one or more local ports to a pod
  proxy           Run a proxy to the Kubernetes API server
  cp              Copy files and directories to and from containers
  auth            Inspect authorization
  debug           Create debugging sessions for troubleshooting workloads and nodes
  events          List events

Advanced Commands:
  diff            Diff the live version against a would-be applied version
  apply           Apply a configuration to a resource by file name or stdin
  patch           Update fields of a resource
  replace         Replace a resource by file name or stdin
  wait            Experimental: Wait for a specific condition on one or many resources
  kustomize       Build a kustomization target from a directory or URL

Settings Commands:
  label           Update the labels on a resource
  annotate        Update the annotations on a resource
  completion      Output shell completion code for the specified shell (bash, zsh, fish, or
powershell)

Subcommands provided by plugins:

Other Commands:
  api-resources   Print the supported API resources on the server
  api-versions    Print the supported API versions on the server, in the form of "group/version"
  config          Modify kubeconfig files
  plugin          Provides utilities for interacting with plugins
  version         Print the client and server version information

Usage:
  kubectl [flags] [options]

Use "kubectl <command> --help" for more information about a given command.
Use "kubectl options" for a list of global command-line options (applies to all commands).

```
 - Uncommon behavior: default help output shows only a subset of commands.
   - Because the cli uses a flat design, there are a large number of commands at the root level, this behavior provides focus on the most commonly used commands. 

## cf help --all -a
```
~ cf help -a
NAME:
   cf - A command line tool to interact with Cloud Foundry

USAGE:
   cf [global options] command [arguments...] [command options]

VERSION:
   8.12.0+636312f.2025-03-28

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

