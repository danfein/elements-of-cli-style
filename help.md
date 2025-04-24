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