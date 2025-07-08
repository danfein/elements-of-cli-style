# Tanzu CLI

Styleguide
```
https://github.com/vmware-tanzu/tanzu-cli/blob/main/docs/plugindev/style_guide.md
```

Install
```
$ brew install vmware-tanzu/tanzu/tanzu-cli
```

Help
```
$  tanzu -h

The Tanzu CLI

Usage:
  tanzu [command]

Available command groups:

  Build
    app                     Applications on Tanzu Platform
    build                   Generate app image from source code
    build-service           plugin to interact with tanzu build service (tbs) crds
    services                Commands for working with services, classes and claims
    workflow                Create, update, view and list Tanzu Supply Chain Workflows.
Requires user to be in a space context.
  Manage
    accelerator             Manage accelerators for Tanzu Platform
    availability-target     Availability-target lifecycle management
    deploy                  Deploy resources
    domain                  tanzu-cli domain plugin
    domain-binding          tanzu-cli domain binding plugin
    external-secrets        interacts with external-secrets.io resources
    gitops                  Gitops operations
    health-probe            HealthProbe lifecycle management
    profile                 Profile lifecycle management
    project                 Create, view, list, use and delete Tanzu projects.
    promote                 Promote resources between contexts
    resource                manage resources in a Kubernetes cluster
    role                    Tanzu Platform Role-Based Access Control
    space                   Tanzu space lifecycle management
    trait                   Trait lifecycle management
  Run
    egress                  Create and manage EgressPoints for Tanzu Platform
    package                 tanzu package management
    route                   Create and manage HTTPRoutes for Tanzu Platform
    secret                  Tanzu secret management
    telemetry               configure cluster-wide settings for vmware tanzu telemetry
  System
    api-token               Manage API Tokens for Tanzu Platform Self-managed
    completion              Output shell completion code
    config                  Configuration for the CLI
    context                 Configure and manage contexts for the Tanzu CLI
    login                   Login to Tanzu Platform for Kubernetes
    plugin                  Manage CLI plugins
    version                 Version information

Flags:
  -h, --help   help for tanzu

Use "tanzu [command] --help" for more information about a command.
```
