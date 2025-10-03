# cf mgmt CLI
https://github.com/vmware-tanzu-labs/cf-mgmt  
>Automation for managing orgs, spaces, users (from ldap groups or internal store) mapping to roles, quotas, application security groups and private-domains that can be driven from concourse pipeline and GIT managed metadata

## Help
```$ cf-mgmt -h
error: Usage:
  cf-mgmt [OPTIONS] <command>

Help Options:
  -h, --help  Show this help message

Available commands:
  add-asg                      *****DEPRECATED, use 'cf-mgmt-config asg instead' - add a named asg to configuration
  add-org                      *****DEPRECATED, use 'cf-mgmt-config org instead' - Adds specified org to configuration
  add-space                    *****DEPRECATED, use 'cf-mgmt-config space instead' - Adds specified space to configuration for org
  asg                          creates/updates a named asg
  clear-users                  updates all configuration but removes any user/group mapping
  delete-org                   deletes org configuration
  delete-space                 deletes space configuration
  generate-concourse-pipeline  generates a concourse pipeline to be used to drive cf-mgmt
  global                       Updates values in cf-mgmt.yml
  init                         Initializes folder structure for configuration
  named-org-quota              creates/updates named org quota
  named-space-quota            creates/updates named space quota
  org                          Adds/updates specified org to configuration
  rename-org                   renames an org
  rename-space                 renames a space for a given org
  space                        adds/updates space configuration
  update-org                   *****DEPRECATED, use 'cf-mgmt-config org instead' - updates org configuration
  update-orgs                  updates orgs.yml
  update-space                 *****DEPRECATED, use 'cf-mgmt-config space instead' - updates space configuration
  version                      Print version information and exit
```