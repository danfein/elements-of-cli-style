# Openshift CLI installation

Docs: https://docs.redhat.com/en/documentation/openshift_container_platform/4.8/html/cli_tools/openshift-cli-oc#cli-installing-cli_cli-developer-commands  

## Homebrew

```
➜  ~ brew install openshift-cli
...
==> Downloading https://ghcr.io/v2/homebrew/core/openshift-cli/manifests/4.18.9
################################################################################################################ 100.0%
==> Fetching openshift-cli
==> Downloading https://ghcr.io/v2/homebrew/core/openshift-cli/blobs/sha256:1492a1a6959104fac9e055b8432d2d3db7d500e1a51
################################################################################################################ 100.0%
==> Pouring openshift-cli--4.18.9.arm64_sequoia.bottle.tar.gz
==> Caveats
zsh completions have been installed to:
  /opt/homebrew/share/zsh/site-functions
==> Summary
🍺  /opt/homebrew/Cellar/openshift-cli/4.18.9: 9 files, 148.8MB
==> Running `brew cleanup openshift-cli`...
Disable this behaviour by setting HOMEBREW_NO_INSTALL_CLEANUP.
Hide these hints with HOMEBREW_NO_ENV_HINTS (see `man brew`).
==> `brew cleanup` has not been run in the last 30 days, running now...
Disable this behaviour by setting HOMEBREW_NO_INSTALL_CLEANUP.
Hide these hints with HOMEBREW_NO_ENV_HINTS (see `man brew`).
Removing: /Users/danielfein/Library/Caches/Homebrew/bootsnap/6ea0ac6c85b22f3a684ba3b54f0e28d0d23a680381c10a8f46e2616c3c18090b... (566 files, 4.6MB)
Removing: /Users/danielfein/Library/Logs/Homebrew/tanzu-cli... (124B)
Removing: /Users/danielfein/Library/Logs/Homebrew/python@3.13... (2 files, 2KB)
Removing: /Users/danielfein/Library/Logs/Homebrew/glib... (64B)
Removing: /Users/danielfein/Library/Logs/Homebrew/fontconfig... (146.9KB)
Removing: /Users/danielfein/Library/Logs/Homebrew/openssl@3... (64B)
Removing: /Users/danielfein/Library/Logs/Homebrew/ca-certificates... (64B)
Pruned 0 symbolic links and 2 directories from /opt/homebrew
```

## From image
```
➜  Downloads tar xvzf openshift-client-mac-arm64-4.18.10.tar.gz
x README.md
x kubectl
x oc

➜  Downloads sudo mv oc /usr/local/bin
Password:
➜  Downloads oc
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
  delete            Delete resources by file names, stdin, resources and names, or by resources and label selector
  scale             Set a new size for a deployment, replica set, or replication controller
  autoscale         Autoscale a deployment config, deployment, replica set, stateful set, or replication controller
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
  completion        Output shell completion code for the specified shell (bash, zsh, fish, or powershell)

Other Commands:
  plugin            Provides utilities for interacting with plugins
  version           Print the client and server version information

Usage:
  oc [flags] [options]

Use "oc <command> --help" for more information about a given command.
Use "oc options" for a list of global command-line options (applies to all commands).

```