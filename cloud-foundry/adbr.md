# Plugin: Application Data Backup and Restore

## Install
```
 $ cf install-plugin -r CF-Community "ApplicationDataBackupRestore"

Searching CF-Community for plugin ApplicationDataBackupRestore...
Plugin ApplicationDataBackupRestore 0.8.0 found in: CF-Community
Attention: Plugins are binaries written by potentially untrusted authors.
Install and use plugins at your own risk.
Do you want to install the plugin ApplicationDataBackupRestore? [yN]: y
Starting download of plugin binary from repository CF-Community...
 11.78 MiB / 11.78 MiB [===============================================================================================================================================] 100.00% 0s
Installing plugin ApplicationDataBackupRestore...
OK

Plugin ApplicationDataBackupRestore 0.8.0 successfully installed.
```
## Help
```
$  cf adbr
Please specify one command of: backup, get-status, list-backups, marketplace or restore

$ cf adbr -h
NAME:
   adbr - application data backup restore operations

USAGE:
   cf adbr marketplace
   cf adbr list-backups SERVICE [-l <num> | --limit <num>] [--unencrypted]
   cf adbr backup SERVICE [--unencrypted]
   cf adbr get-status SERVICE [--unencrypted]
   cf adbr restore SERVICE BACKUP-ID [-r full-only|latest | --restore-point=full-only|latest] [--force] [--unencrypted]
```

## Errors
```
$  cf adbr
Failed to get CF metadata. Please ensure you are logged in and targeting an org/space. Error: Authentication has expired.  Please log back in to re-authenticate.

TIP: Use `cf login -a <endpoint> -u <user> -o <org> -s <space>` to log back in and re-authenticate.%
```

## Marketplace
```
$ cf adbr marketplace
Getting services from marketplace in org name-of-org / space UX Team Space as daniel.fein@name.com...

service                 supports ADBR
app-autoscaler          no
smb                     no
p-identity              no
credhub                 no
p.rabbitmq              no
p.config-server         no
p.service-registry      no
p.gateway               no
p-dataflow              no
p-dataflow-messaging    no
p-dataflow-relational   no
postgres                yes
p-cloudcache            no
p-redis                 no
p.redis                 no
genai                   no
p.mysql                 yes
scheduler-for-pcf       no
```