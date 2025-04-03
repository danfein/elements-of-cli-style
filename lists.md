# Lists


## Tanzu Profile get
```
$ tanzu profile get apps.tanzu.vmware.com --cluster-groups
📡 Overview
   name:           apps.tanzu.vmware.com
   description:    The Apps profile enables you to deploy applications built as ContainerApps using Tanzu Build.
   ready:          True
   last updated:   2d16h ago

🧱 Required Capabilities
   container-app.tanzu.vmware.com
   egress.tanzu.vmware.com
   health.spaces.tanzu.vmware.com
   horizontal-autoscaling.tanzu.vmware.com
   ingress.tanzu.vmware.com
   k8sgateway.tanzu.vmware.com
   mtls.tanzu.vmware.com
   package-management.tanzu.vmware.com
   prometheus-operator.tanzu.vmware.com
   tanzu-servicebinding.tanzu.vmware.com

📗 Traits
   carvel-package-installer.tanzu.vmware.com - Resolved

🎯 Cluster Groups Compatibility
   build-cluster-group - Unschedulable
     Missing capabilities:   container-app.tanzu.vmware.com, health.spaces.tanzu.vmware.com, horizontal-autoscaling.tanzu.vmware.com, ingress.tanzu.vmware.com, k8sgateway.tanzu.vmware.com, mtls.tanzu.vmware.com, prometheus-operator.tanzu.vmware.com, tanzu-servicebinding.tanzu.vmware.com

   run - Schedulable

   tnz-24865-petertran - Unschedulable
     Missing capabilities:   container-app.tanzu.vmware.com, egress.tanzu.vmware.com, health.spaces.tanzu.vmware.com, horizontal-autoscaling.tanzu.vmware.com, ingress.tanzu.vmware.com, k8sgateway.tanzu.vmware.com, mtls.tanzu.vmware.com, package-management.tanzu.vmware.com, prometheus-operator.tanzu.vmware.com, tanzu-servicebinding.tanzu.vmware.com

```