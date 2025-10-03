# kf CLI
A cf-like experience on k8s  
The Kf CLI allows users to interact with Kf applications and services deployed on a Kubernetes cluster.  
https://cloud.google.com/migrate/kf/docs/2.5/documentation

## Install 
```
$ gcloud storage cp gs://kf-releases/v2.5.4/kf-darwin /tmp/kf
Copying gs://kf-releases/v2.5.4/kf-darwin to file:///tmp/kf
  Completed files 1/1 | 63.1MiB/63.1MiB

Average throughput: 43.7MiB/s
$ chmod a+x /tmp/kf

$ sudo mv /tmp/kf /usr/local/bin/kf

```

## Help

```

App Management
  push                         Create a new App or apply updates to an existing one.
  delete                       Delete the App with the given name in the targeted Space.
  apps                         List Apps in the targeted Space.
  app                          Print information about the given App.
  start                        Deploy a stopped App and route traffic to it once healthy.
  stop                         Remove instances of a running App and stop network traffic.
  restart                      Restart each running instance of an App without downtime.
  restage                      Rebuild and redeploy an App without downtime.
  scale                        Change the horizontal or vertical scale of an App without downtime.
  logs                         Show logs for an App.
  proxy                        Start a local reverse proxy to an App.

Auto Scale
  enable-autoscaling           Enable autoscaling for App.
  disable-autoscaling          Disable autoscaling for App.
  create-autoscaling-rule      Create autoscaling rule for App.
  delete-autoscaling-rules     Delete all autoscaling rules for App and disable autoscaling.
  update-autoscaling-limits    Update autoscaling limits for App.

Environment Variables
  env                          Print information about an App's environment variables.
  set-env                      Create or update an environment variable for an App.
  unset-env                    Delete an environment variable on an App.

Buildpacks
  buildpacks                   List buildpacks in the targeted Space.
  stacks                       List stacks in the targeted Space.

Routing
  routes                       List routes in the targeted Space.
  create-route                 Create a traffic routing rule for a host+path pair.
  delete-route                 Delete a Route in the targeted Space.
  delete-orphaned-routes       Delete Routes with no App bindings.
  map-route                    Grant an App access to receive traffic from the Route.
  unmap-route                  Revoke an App's access to receive traffic from the Route.
  proxy-route                  Start a local reverse proxy to a Route.
  domains                      List domains that can be used in the targeted Space.

Services
  create-service               Create a service instance from a marketplace template.
  create-user-provided-service Create a standalone service instance from existing credentials.
  update-user-provided-service Update a standalone service instance with new credentials.
  delete-service               Delete the ServiceInstance with the given name in the targeted Space.
  service                      Print information about the given ServiceInstance.
  services                     List services in the targeted Space.
  marketplace                  List service classes available in the cluster.

Service Bindings
  bind-service                 Grant an App access to a service instance.
  bind-route-service           Bind a route service instance to an HTTP route.
  bindings                     List bindings in the targeted Space.
  unbind-service               Revoke an App's access to a service instance.
  unbind-route-service         Unbind a route service instance from an HTTP route.
  vcap-services                Print the VCAP_SERVICES environment variable for an App.

Service Brokers
  create-service-broker        Add a service broker to the marketplace.
  delete-service-broker        Remove a service broker from the marketplace.

Spaces
  target                       Set the default Space to run commands against.
  spaces                       List Spaces in the cluster.
  space                        Print information about the given Space.
  create-space                 Create a Space with the given name.
  delete-space                 Delete the Space with the given name.
  configure-space              Set configuration for a Space.
  space-users                  List users and their roles in a Space.
  set-space-role               Assgin a Role to a Subject (User|Group|ServiceAccount).
  unset-space-role             Unassign a Role to a Subject.


Cluster
  configure-cluster            Set configuration for a cluster.

Builds
  builds                       List Builds in the targeted Space.
  build-logs                   Get the logs of the given Build.
  build                        Print information about the given Build.

Network Policies
  network-policies             List network policies in the targeted Space.
  delete-network-policy        Delete the NetworkPolicy with the given name in the targeted Space.
  network-policy               Print information about the given NetworkPolicy.

Tasks
  run-task                     Run a short-lived Task on the App.
  terminate-task               Terminate a running Task.
  tasks                        List Tasks in the targeted Space.

[PREVIEW] Jobs
  create-job                   Create a Job on the App.
  run-job                      Run the Job once.
  schedule-job                 Schedule the Job for execution on a cron schedule.
  jobs                         List Jobs in the targeted Space.
  job-schedules                List job schedules in the targeted Space.
  job-history                  List the execution history of a Job.
  delete-job                   Delete the Job with the given name in the targeted Space.
  delete-job-schedule          Delete the schedule for a Job.

Other Commands
  doctor                       Run validation tests against one or more components.
  version                      Print the CLI version.
  debug                        Print debugging information useful for filing a bug report.
  login                        Log in to a Kubernetes cluster interactively.
  api                          Target a Kubernetes cluster API endpoint.
  auth                         Manually authenticate to a Kubernetes cluster.
  logout                       Log out of a Kubernetes cluster.
  migrate                      CF to Kf migration tools.
  third-party-licenses         Print third party license information.
  about                        Print information about Kf's terms of service.
  ssh                          Open a shell on an App instance.

Usage:
  kf [flags] COMMAND

Use "kf COMMAND --help" for more information about a given command.
```