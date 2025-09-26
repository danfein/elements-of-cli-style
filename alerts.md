# Alerts and Notices

## gcloud cli 

```
$ gcloud container clusters get-credentials tap1-1-0-cluster --region us-east4 --project pivotal-knative
Fetching cluster endpoint and auth data.
kubeconfig entry generated for tap1-1-0-cluster.


Updates are available for some Google Cloud CLI components.  To install them,
please run:
  $ gcloud components update

```

Update prompt shown when running commands

## Brew (macOS package manager)

```
…
The uninstallation processes requires administrative privileges
because some of the installed files cannot be removed by a normal
user. You may be prompted for your password now...
…
```

Notice shown when running an upgrade

## Kubectl plugin installation

```
~ kubectl krew install ctx
Updated the local copy of plugin index.
Installing plugin: ctx
Installed plugin: ctx
\
 | Use this plugin:
 | 	kubectl ctx
 | Documentation:
 | 	https://github.com/ahmetb/kubectx
 | Caveats:
 | \
 |  | If fzf is installed on your machine, you can interactively choose
 |  | between the entries using the arrow keys, or by fuzzy searching
 |  | as you type.
 |  | See https://github.com/ahmetb/kubectx for customization and details.
 | /
/
WARNING: You installed plugin "ctx" from the krew-index plugin repository.
   These plugins are not audited for security by the Krew maintainers.
   Run them at your own risk.
```