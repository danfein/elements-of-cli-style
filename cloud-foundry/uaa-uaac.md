# UAA and UAAC (UAA CLI)

Install
```

```

help
```
uaac

UAA Command Line Interface

Miscellaneous
  version                          Display version
  help [topic|command...]          Display summary or details of command or topic
  target [uaa_url]                 Display current or set new target
                                   -f | --[no-]force, set even if target does not respond
                                   --ca-cert [file], use the given CA certificate to validate the target's SSL certificate
                                   --skip-ssl-validation, do not attempt to validate ssl certificate
                                   --[no-]basic_auth, set if you need basic or oauth2 (url encoded) client authentication
  targets                          Display all targets
  context [name]                   Display or set current context
  contexts                         Display all contexts

System Information
  info                             get information about current target
  me                               get authenticated user information
  prompts                          Show prompts for credentials required for implicit grant post
  signing key                      get the UAA's token signing key(s)
                                   -c | --client <name>
                                   -s | --secret <secret>, client secret
  password strength [password]     calculate strength score of a password

Tokens
  token get [credentials...]       Gets a token by posting user credentials with an implicit grant request
                                   -c | --client <name>
                                   --scope <list>
  token client get [id]            Gets a token with client credentials grant
                                   -s | --secret <secret>, client secret
                                   --scope <list>
  token owner get [client] [user]  Gets a token with a resource owner password grant
                                   -s | --secret <secret>, client secret
                                   -p | --password <password>, user password
                                   --scope <list>
  token sso get [client]           Gets a token based on a one time passcode after successful SSO via browser
                                   -s | --secret <secret>, client secret
                                   --passcode <passcode>
                                   --scope <list>
  token refresh [refreshtoken]     Gets a new access token from a refresh token
                                   -c | --client <name>
                                   -s | --secret <secret>, client secret
                                   --scope <list>
  token authcode get               Gets a token using the authcode flow with browser
                                   -c | --client <name>
                                   -s | --secret <secret>, client secret
                                   --scope <list>
                                   --[no-]cf, save token in the ~/.cf_tokens file
                                   --port <number>, pin internal server to specific port
  token implicit get               Gets a token using the implicit flow with browser
                                   -c | --client <name>
                                   --scope <list>
                                   --[no-]cf, save token in the ~/.cf_tokens file
                                   --port <number>, pin internal server to specific port
  token decode [token] [tokentype] Show token contents as parsed locally or by the UAA. Decodes locally unless --client and
                                   --secret are given. Validates locally if --key given or server's signing key has been
                                   retrieved
                                   --key <key>, Token validation key
                                   -c | --client <name>
                                   -s | --secret <secret>, client secret
  token delete [contexts...]       Delete current or specified context tokens and settings
                                   --[no-]all, remove all contexts

User Accounts
  users [filter]                   List user accounts
                                   -a | --attributes <names>, output for each user
                                   --start <number>, start of output page
                                   --count <number>, max number per page
  user get [name]                  Get specific user account
                                   --origin <name>, select user to update by identity provider origin. Defaults to UAA
                                   -a | --attributes <names>, output for each user
  user add [name]                  Add a user account
                                   --origin <name>, select user to update by identity provider origin. Defaults to UAA
                                   --given_name <name>
                                   --family_name <name>
                                   --emails <addresses>
                                   --phones <phone_numbers>
                                   -p | --password <password>, user password
  user update [name]               Update a user account with specified options
                                   --origin <name>, select user to update by identity provider origin. Defaults to UAA
                                   --given_name <name>
                                   --family_name <name>
                                   --emails <addresses>
                                   --phones <phone_numbers>
                                   --del_attrs <attr_names>, list of attributes to delete
  user delete [name]               Delete user account
                                   --origin <name>, select user to update by identity provider origin. Defaults to UAA
  user ids [username|id...]        Gets user names and ids for the given users
  user unlock [name]               Unlocks the user account
  user deactivate [name]           Deactivates user
  user activate [name]             Activates user
  password set [name]              Set password
                                   -p | --password <password>, user password
  password change                  Change password for authenticated user in current context
                                   -o | --old_password <password>, current password
                                   -p | --password <password>, user password

Groups
  groups [filter]                  List groups
                                   -a | --attributes <names>, output for each user
                                   --start <start>, show results starting at this index
                                   --count <count>, number of results to show
  group get [name]                 Get specific group information
                                   -a | --attributes <names>, output for each user
  group add [name]                 Adds a group
  group delete [name]              Delete group
  group mappings                   List all the mappings between uaa scopes and external groups
                                   --start <start>, show results starting at this index
                                   --count <count>, number of results to show
  group map [external_group]       Map uaa groups to external groups
                                   --id <id>, map uaa group using group id
                                   --name <name>, map uaa scope using group name
                                   --origin <origin>, map uaa scope to external group for this origin. Defaults to ldap.
  group unmap [group_name] [external_group]
                                   Unmaps an external group from a uaa group
                                   --origin <origin>, map uaa scope to external group for this origin. Defaults to ldap.
  member add [name] [users...]     add members to a group
  member delete [name] [users...]  remove members from a group

Client Application Registrations
  clients [filter]                 List client registrations
                                   -a | --attributes <names>, output for each user
                                   --start <start>, show results starting at this index
                                   --count <count>, number of results to show
  client get [id]                  Get specific client registration
                                   -a | --attributes <names>, output for each user
  client add [id]                  Add client registration
                                   --name <string>
                                   --scope <list>
                                   --authorized_grant_types <list>
                                   --authorities <list>
                                   --access_token_validity <seconds>
                                   --refresh_token_validity <seconds>
                                   --redirect_uri <list>
                                   --autoapprove <list>
                                   --allowpublic <list>
                                   --allowedproviders <list>
                                   --signup_redirect_url <url>
                                   --required_user_groups <list>
                                   --clone <other>, get default settings from other
                                   -s | --secret <secret>, client secret
                                   -i | --[no-]interactive, interactively verify all values
  client update [id]               Update client registration
                                   --name <string>
                                   --scope <list>
                                   --authorized_grant_types <list>
                                   --authorities <list>
                                   --access_token_validity <seconds>
                                   --refresh_token_validity <seconds>
                                   --redirect_uri <list>
                                   --autoapprove <list>
                                   --allowpublic <list>
                                   --allowedproviders <list>
                                   --signup_redirect_url <url>
                                   --required_user_groups <list>
                                   --del_attrs <attr_names>, list of attributes to delete
                                   -i | --[no-]interactive, interactively verify all values
  client delete [id]               Delete client registration
  secret set [id]                  Set client secret
                                   -s | --secret <secret>, client secret
  secret change                    Change secret for authenticated client in current context
                                   --old_secret <secret>, current secret
                                   -s | --secret <secret>, client secret
  client jwt add [id]              Add client jwt trust
                                   --jwks_uri <token_keys endpoint>, JWKS token key endpoint
                                   --jwks <json token key set>, JWKS token key
                                   --issuer <Issuer>, Issuer to trust
                                   --subject <Subject>, Subject to trust
                                   --audience <Audience>, Audience to trust
  client jwt update [id]           Update client jwt trust
                                   --jwks_uri <token_keys endpoint>, JWKS token key endpoint
                                   --jwks <json token key set>, JWKS token key
                                   --issuer <Issuer>, Issuer to trust
                                   --subject <Subject>, Subject to trust
                                   --audience <Audience>, Audience to trust
  client jwt delete [id]           Delete client jwt trust
                                   --kid <key id in json token keys>, JWKS token key
                                   --jwks <json token key set>, JWKS token key
                                   --issuer <Issuer>, Issuer to trust
                                   --subject <Subject>, Subject to trust
                                   --audience <Audience>, Audience to trust

CURL
  curl [path]                      CURL to a UAA endpoint
                                   -X | --request <method>, request method type, defaults to GET
                                   -d | --data <data>, data included in request body
                                   -H | --header <header>, header to be included in the request
                                   -k | --insecure, makes request without verifying SSL certificates
                                   -C | --cacert <ca_file>, CA certificate to verify peer against
                                   -b | --bodyonly, show body only in response

Global options:
  -h | --[no-]help                 display helpful information
  -v | --[no-]version              show version
  -d | --[no-]debug                display debug information
  -t | --[no-]trace                display extra verbose debug information
  --config [string|file]           file to get/save configuration information or yaml string
  -z | --zone <subdomain>          subdomain of zone to manage

```