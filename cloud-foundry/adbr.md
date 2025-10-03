# Plugin: Application Data Backup and Restore
https://techdocs.broadcom.com/us/en/vmware-tanzu/data-solutions/tanzu-for-postgres-on-cloud-foundry/1-2/postgres-1-2/backup-restore-adbr.html

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

## Backup
```
$ cf abdr backup acme-pg --unencrypted
OK
```

## Restore
```
--- help ---
cf adbr restore -h
NAME:
   adbr - application data backup restore operations

USAGE:
   cf adbr marketplace
   cf adbr list-backups SERVICE [-l <num> | --limit <num>] [--unencrypted]
   cf adbr backup SERVICE [--unencrypted]
   cf adbr get-status SERVICE [--unencrypted]
   cf adbr restore SERVICE BACKUP-ID [-r full-only|latest | --restore-point=full-only|latest] [--force] [--unencrypted]

--- restore ---
$ cf abdr restore acme-pg 1234-5678 -r latest
Restoring service instance RESTORE_SERVICE_NAME in org $ORG / space $SPACE as $USER...
This action will overwrite all data in this service instance.
Really restore the service instance RESTORE_SERVICE_NAME? [yN]: y
OK
```


## Errors
```
--- No auth ---
$  cf adbr
Failed to get CF metadata. Please ensure you are logged in and targeting an org/space. Error: Authentication has expired.  Please log back in to re-authenticate.

TIP: Use `cf login -a <endpoint> -u <user> -o <org> -s <space>` to log back in and re-authenticate.%

--- Missing Flags ---
$ cf adbr restore
the required arguments `SERVICE` and `BACKUP-ID` were not provided


--- Backup while service is being created ---
$ cf adbr backup acme-pg --unencrypted
Failed to backup service instance "acme-pg": failed due to server error, status code: 500

--- server error ---
$ cf adbr list-backups acme-pg
Failed to list backups for service instance "acme-pg": failed due to server error, status code: 400

$ cf adbr get-status acme-pg
Getting status of service instance acme-pg in org dftest / space dftest as daniel.fein@name.com...
Backup ID                                         Time of Backup                 Status          Reason
e2e61d90-80de-404a-9193-8c5182aba824_1758910345   Fri Sep 26 18:12:34 UTC 2025   Backup failed   failed to upload artifact: RequestError: send request failed
                                                                                                 caused by: Put "https://dummy.s3.endpoint_url.value/dummy.s3.bucket_name.value/dummy.path.value/postgres/service-instance_e2e61d90-80de-404a-9193-8c5182aba824/2025/09/26/e2e61d90-80de-404a-9193-8c5182aba824_1758910345/artifact": dial tcp: lookup dummy.s3.endpoint_url.value on 169.254.0.2:53: no such host

```