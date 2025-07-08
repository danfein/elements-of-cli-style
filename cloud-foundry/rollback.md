# Rollback cf app

## Manual rollback
### Check available droplets
```
$ cf droplets training-app
Getting droplets of app training-app in org student-pqvsjp / space default as student-pqvsjp...

guid                                             state    created
d2c62987-c8c0-45e2-a47c-a7ee14f8d36a (current)   staged   Tue 06 May 22:19:56 UTC 2025
104916f5-ff97-425b-83a1-00f7f22c1ef2             staged   Tue 06 May 22:14:02 UTC 2025
```

### Stop App
```
$ cf stop training-app
Stopping app training-app in org student-pqvsjp / space default as student-pqvsjp...
OK
```

### Set Droplet
```
$ cf set-droplet training-app 104916f5-ff97-425b-83a1-00f7f22c1ef2
Setting app training-app to droplet 104916f5-ff97-425b-83a1-00f7f22c1ef2 in org student-pqvsjp / space default as student-pqvsjp...
OK
```

### Restart App
```
cf start training-app
Starting app training-app in org student-pqvsjp / space default as student-pqvsjp...

Waiting for app to start...

Instances starting...
Instances starting...

name:              training-app
requested state:   started
routes:            
last uploaded:     Tue 06 May 22:14:02 UTC 2025
stack:             cflinuxfs4
buildpacks:        
        name           version   detect output   buildpack name
        go_buildpack   1.10.26   go              go

type:           web
sidecars:       
instances:      3/3
memory usage:   48M
     state     since                  cpu    memory      disk         logging        cpu entitlement   details
#0   running   2025-05-06T22:27:30Z   0.0%   0B of 48M   0B of 256M   0B/s of 0B/s   0.0%              
#1   running   2025-05-06T22:27:29Z   0.0%   0B of 0B    0B of 0B     0B/s of 0B/s   0.0%              
#2   running   2025-05-06T22:27:29Z   0.0%   0B of 48M   0B of 256M   0B/s of 0B/s   0.0% 

--- verify ---
$ cf droplets training-app
Getting droplets of app training-app in org student-pqvsjp / space default as student-pqvsjp...

guid                                             state    created
d2c62987-c8c0-45e2-a47c-a7ee14f8d36a             staged   Tue 06 May 22:19:56 UTC 2025
104916f5-ff97-425b-83a1-00f7f22c1ef2 (current)   staged   Tue 06 May 22:14:02 UTC 2025
```

## Use Revisions to roll back
```
--- list ---
$ cf revisions training-app
Getting revisions for app training-app in org student-pqvsjp / space default as student-pqvsjp...

revision      description                                                 deployable   revision guid                          created at
4(deployed)   New droplet deployed. New environment variables deployed.   true         fc97447e-6ed5-476e-a5d4-a63d13595864   2025-05-06T22:31:23Z
3             New droplet deployed.                                       true         9bb22e08-90a5-4bf7-a9b3-bfd1509d140f   2025-05-06T22:27:07Z
2             New droplet deployed.                                       true         15437564-c7d3-45cc-b57f-d10a25dad0bf   2025-05-06T22:20:03Z
1             Initial revision.                                           true         94b91422-7ba6-4990-b9ff-324b2a9712e4   2025-05-06T22:18:20Z

--- rollback ---

```