# cf apps commands and output

## cf apps
```
$ cf apps
Getting apps in org group df-og / space group postfacto  as user-name...
OK

name           requested state   instances   memory   disk   urls
training-app   started           3/3         48M      256M   training-app.apps.example-name.cf-app.com
```
- instances is running/desired; a stopped app shows `0/N` with a blank urls column.

## cf app
```
$ cf app training-app
Showing health and status for app training-app in org group df-og / space group postfacto  as user-name...

name:              training-app
requested state:   started
routes:            training-app.apps.example-name.cf-app.com
last uploaded:     Wed 06 Aug 14:22:10 UTC 2025
stack:             cflinuxfs4
buildpacks:        
        name           version   detect output   buildpack name
        go_buildpack   1.10.26   go              go

type:           web
sidecars:       
instances:      3/3
memory usage:   48M
     state     since                  cpu    memory      disk            logging         cpu entitlement   details
#0   running   2025-08-06T14:23:01Z   0.2%   9M of 48M   10.8M of 256M   0B/s of 16K/s   12.3%             
#1   running   2025-08-06T14:22:59Z   0.1%   9M of 48M   10.8M of 256M   0B/s of 16K/s   8.0%              
#2   running   2025-08-06T14:23:01Z   0.1%   9M of 48M   10.8M of 256M   0B/s of 16K/s   9.5%              
```
- cpu entitlement is the share of the instance's cpu quota consumed, not raw cpu%.

## cf push
```
$ cf push training-app
Pushing app training-app to org group df-og / space group postfacto  as user-name...

Creating app with these attributes...
+ name:         training-app
  path:         /Users/user-name/workspace/training-app
+ buildpacks:
+   go_buildpack

Creating app training-app...
Mapping routes...
Comparing local files to remote cache...
Packaging files to upload...
Uploading files...

Waiting for API to complete processing files...

Staging app and tracing logs...
   Downloading go_buildpack...
   Downloaded go_buildpack
   -----> Go Buildpack version 1.10.26
   -----> Installing go 1.22.10
   Exit status 0
   Uploading droplet, build artifacts cache...
   Uploading complete

Waiting for app to start...

name:              training-app
requested state:   started
routes:            training-app.apps.example-name.cf-app.com
last uploaded:     Wed 06 Aug 14:22:10 UTC 2025
stack:             cflinuxfs4
buildpacks:        
        name           version   detect output   buildpack name
        go_buildpack   1.10.26   go              go

type:           web
sidecars:       
instances:      1/1
memory usage:   48M
     state     since                  cpu    memory     disk        logging        cpu entitlement   details
#0   running   2025-08-06T14:23:20Z   0.0%   0B of 48M  0B of 256M  0B/s of 0B/s   0.0%              
```
- see cloud-foundry/cf-push.md for the full component-by-component (create-app/package/stage/set-droplet) walkthrough; this is the plain one-shot push.

## cf start
```
$ cf start training-app
Starting app training-app in org group df-og / space group postfacto  as user-name...

Waiting for app to start...

Instances starting...
Instances starting...

name:              training-app
requested state:   started
routes:            training-app.apps.example-name.cf-app.com
last uploaded:     Wed 06 Aug 14:22:10 UTC 2025
stack:             cflinuxfs4
buildpacks:        
        name           version   detect output   buildpack name
        go_buildpack   1.10.26   go              go

type:           web
sidecars:       
instances:      3/3
memory usage:   48M
     state     since                  cpu    memory      disk            logging         cpu entitlement   details
#0   running   2025-08-06T14:23:01Z   0.1%   9M of 48M   10.8M of 256M   0B/s of 16K/s   9.0%              
#1   running   2025-08-06T14:23:01Z   0.1%   9M of 48M   10.8M of 256M   0B/s of 16K/s   9.0%              
#2   running   2025-08-06T14:23:02Z   0.1%   9M of 48M   10.8M of 256M   0B/s of 16K/s   9.0%              
```

## cf stop
```
$ cf stop training-app
Stopping app training-app in org group df-og / space group postfacto  as user-name...
OK
```

## cf restart
```
$ cf restart training-app
Restarting app training-app in org group df-og / space group postfacto  as user-name...

Stopping app...

Waiting for app to start...

Instances starting...

name:              training-app
requested state:   started
routes:            training-app.apps.example-name.cf-app.com
last uploaded:     Wed 06 Aug 14:22:10 UTC 2025
stack:             cflinuxfs4
buildpacks:        
        name           version   detect output   buildpack name
        go_buildpack   1.10.26   go              go

type:           web
sidecars:       
instances:      3/3
memory usage:   48M
     state     since                  cpu    memory      disk            logging         cpu entitlement   details
#0   running   2025-08-06T14:25:10Z   0.0%   0B of 48M   0B of 256M     0B/s of 0B/s    0.0%              
#1   running   2025-08-06T14:25:09Z   0.0%   0B of 48M   0B of 256M     0B/s of 0B/s    0.0%              
#2   running   2025-08-06T14:25:10Z   0.0%   0B of 48M   0B of 256M     0B/s of 0B/s    0.0%              
```
- restart stops and starts the running droplet; it does not restage, unlike `cf restage`.

## cf restage
```
$ cf restage training-app
This action will cause app downtime.

Restaging app training-app in org group df-og / space group postfacto  as user-name...

Staging app and tracing logs...
   Downloading go_buildpack...
   Downloaded go_buildpack
   -----> Go Buildpack version 1.10.26
   -----> Installing go 1.22.10
   Exit status 0
   Uploading droplet, build artifacts cache...
   Uploading complete

Waiting for app to start...

name:              training-app
requested state:   started
routes:            training-app.apps.example-name.cf-app.com
last uploaded:     Wed 06 Aug 14:30:44 UTC 2025
stack:             cflinuxfs4
buildpacks:        
        name           version   detect output   buildpack name
        go_buildpack   1.10.26   go              go

type:           web
sidecars:       
instances:      3/3
memory usage:   48M
     state     since                  cpu    memory      disk            logging         cpu entitlement   details
#0   running   2025-08-06T14:31:02Z   0.1%   9M of 48M   10.8M of 256M   0B/s of 16K/s   10.2%             
#1   running   2025-08-06T14:31:01Z   0.1%   9M of 48M   10.8M of 256M   0B/s of 16K/s   11.0%             
#2   running   2025-08-06T14:31:02Z   0.1%   9M of 48M   10.8M of 256M   0B/s of 16K/s   10.2%             
```

## cf scale
```
$ cf scale training-app
Showing current scale of app training-app in org group df-og / space group postfacto  as user-name...

     memory   disk   instances
web  48M      256M   3/3
```

## cf scale (resize)
```
$ cf scale training-app -i 5 -m 512M -k 1G
Scaling training-app in org group df-og / space group postfacto  as user-name...
This will cause the app to restart. Are you sure you want to scale training-app? [yN]: y

Scaling training-app in org group df-og / space group postfacto  as user-name...

     memory   disk   instances
web  512M     1G     5/5
```
- memory/disk changes trigger a restart; use `-f` to skip the confirmation prompt.

## cf rename
```
$ cf rename training-app training-app-v2
Renaming app training-app to training-app-v2 in org group df-og / space group postfacto  as user-name...
OK
```

## cf delete
```
$ cf delete training-app
Really delete the app training-app? [yN]: y
Deleting app training-app in org group df-og / space group postfacto  as user-name...
OK
```
- answering `n` leaves the app in place and prints `App 'training-app' has not been deleted.`

## cf env
```
$ cf env training-app
Getting env variables for app training-app in org group df-og / space group postfacto  as user-name...

System-Provided:
{
 "VCAP_APPLICATION": {
  "application_id": "6f8b2b13-6e2a-4a1a-9e2f-2b6a2b3c4d5e",
  "application_name": "training-app",
  "organization_name": "df-og",
  "space_name": "postfacto",
  "uris": [
   "training-app.apps.example-name.cf-app.com"
  ]
 }
}

User-Provided:
TRAINING_KEY: training-value

No running env variables have been set

No staging env variables have been set
```

## cf set-env
```
$ cf set-env training-app TRAINING_KEY training-value
Setting env variable TRAINING_KEY for app training-app in org group df-og / space group postfacto  as user-name...
OK
TIP: Use 'cf restage' to ensure your env variable changes take effect.
```

## cf unset-env
```
$ cf unset-env training-app TRAINING_KEY
Removing env variable TRAINING_KEY from app training-app in org group df-og / space group postfacto  as user-name...
OK
TIP: Use 'cf restage' to ensure your env variable changes take effect.
```

## cf logs
```
$ cf logs training-app
Retrieving logs for app training-app in org group df-og / space group postfacto  as user-name...

2025-08-06T14:23:20.11-0700 [APP/PROC/WEB/0] OUT Listening on port 8080
2025-08-06T14:23:21.03-0700 [RTR/0]          OUT training-app.apps.example-name.cf-app.com - [06/Aug/2025:21:23:21.000 +0000] "GET / HTTP/1.1" 200 0 15 "-" "curl/8.4.0" 10.0.1.5:61234 -> 10.0.2.10:8080 x_forwarded_for:"-" x_forwarded_proto:"https" vcap_request_id:"a1b2c3d4-e5f6-7890-abcd-ef1234567890" response_time:0.002145
^C
```
- streams until interrupted; ctrl-C to exit.

## cf logs --recent
```
$ cf logs training-app --recent
Retrieving logs for app training-app in org group df-og / space group postfacto  as user-name...

2025-08-06T14:20:01.00-0700 [API/0]          OUT Created app with guid 6f8b2b13-6e2a-4a1a-9e2f-2b6a2b3c4d5e
2025-08-06T14:22:10.44-0700 [STG/0]          OUT Downloading go_buildpack...
2025-08-06T14:23:20.11-0700 [APP/PROC/WEB/0] OUT Listening on port 8080
```
- dumps the buffered recent log lines and returns immediately.

## cf events
```
$ cf events training-app
Getting events for app training-app in org group df-og / space group postfacto  as user-name...

time                          event                actor       description
2025-08-06T14:31:02.00-0700   audit.app.restage    user-name   
2025-08-06T14:23:21.00-0700   audit.app.start      user-name   instances: 3, memory: 48M, disk: 256M
2025-08-06T14:20:01.00-0700   audit.app.create     user-name   name: training-app, instances: 3, memory: 48M, state: STOPPED
```

## cf ssh
```
$ cf ssh training-app

vcap@6f8b2b13-6e2a-4a1a-9e2f-2b6a2b3c4d5e:~$ ls
app  deps  logs  staging_info.yml  tmp
vcap@6f8b2b13-6e2a-4a1a-9e2f-2b6a2b3c4d5e:~$ exit
logout
```
- requires the app to have a running instance and the `ssh` feature flag enabled.

## cf buildpacks
```
$ cf buildpacks
Getting buildpacks as user-name...

position   name               stack        enabled   locked   filename
1          go_buildpack       cflinuxfs4   true      false    go_buildpack-cflinuxfs4-v1.10.26.zip
2          java_buildpack     cflinuxfs4   true      false    java-buildpack-v4.79.zip
3          nodejs_buildpack   cflinuxfs4   true      false    nodejs_buildpack-cflinuxfs4-v1.8.19.zip
4          python_buildpack   cflinuxfs4   true      false    python_buildpack-cflinuxfs4-v1.7.55.zip
```
- buildpacks and stacks are foundation-level, not scoped to an org group / space group.

## cf stacks
```
$ cf stacks
Getting stacks as user-name...

name         description
cflinuxfs4   Cflinuxfs4 Test Stack
```

## cf create-app-manifest
```
$ cf create-app-manifest training-app
Creating an app manifest for app training-app in org group df-og / space group postfacto  as user-name...
Manifest file created successfully at /Users/user-name/training-app_manifest.yml
```
