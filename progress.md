# Progress

## Git (version control)

```
❯ git clone git@github.com:danfein/elements-of-cli-style.git
Cloning into 'elements-of-cli-style'...
remote: Enumerating objects: 3, done.
remote: Counting objects: 100% (3/3), done.
remote: Compressing objects: 100% (2/2), done.
Receiving objects: 100% (3/3), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
```
Shows milestones, with updating counters for progress.
Summarizes work done at end.

## Tanzu plugin install
```
tanzu plugin install --group vmware-tanzu/app-developer
[i] The following plugins will be installed from plugin group 'vmware-tanzu/app-developer:v1.1.0'
  NAME            TARGET      VERSION
  acceleratorv2   global      v2.0.1
  appsv2          global      v0.22.0
  build           global      v0.18.5
  domain          global      v0.2.6
  domain-binding  global      v0.1.6
  egress          global      v0.0.7
  package         kubernetes  v0.36.1
  project         global      v0.3.3
  rbac            global      v0.2.5
  resource        global      v0.6.3
  route           global      v0.0.7
  secret          kubernetes  v0.33.5
  services        kubernetes  v0.15.0
  space           global      v0.6.1
  workflow        global      v0.1.5
[i] Installed plugin 'acceleratorv2:v2.0.1' with target 'global'
[i] Installed plugin 'appsv2:v0.22.0' with target 'global'
[i] Installed plugin 'build:v0.18.5' with target 'global'
[i] Installed plugin 'domain:v0.2.6' with target 'global'
[i] Installed plugin 'domain-binding:v0.1.6' with target 'global'
\ Installing plugin 'egress:v0.0.7' with target 'global'
...
[ok] successfully installed all plugins from group 'vmware-tanzu/app-developer:v1.1.0'
```
Spinner indicator while runing, confirmation message when complete.