# Users

## Org
```
$ cf org-users df-test
Getting users in org df-test as push_apps_manager...

ORG MANAGER
  tanzu_platform_admin (uaa)

BILLING MANAGER
  No BILLING MANAGER found

ORG AUDITOR
  No ORG AUDITOR found
```

## Space
```
cf space-users df-test df-test-space
Getting users in org df-test / space df-test-space as push_apps_manager...

SPACE MANAGER
  tanzu_platform_admin (uaa)

SPACE DEVELOPER
  tanzu_platform_admin (uaa)

SPACE SUPPORTER
  No SPACE SUPPORTER found

SPACE AUDITOR
  No SPACE AUDITOR found
  ```