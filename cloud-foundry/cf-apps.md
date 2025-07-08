# CF Apps

## cf app
```
cf app training-app
Showing health and status for app training-app in org student-pqvsjp / space default as student-pqvsjp...

name:              training-app
requested state:   started
routes:            training-app-courteous-kangaroo-ne.apps.zone-3924730.cf-app.com, training-app.student-pqvsjp.220af0b6.nip.io
last uploaded:     Tue 06 May 20:55:41 UTC 2025
stack:             cflinuxfs4
buildpacks:        
        name           version   detect output   buildpack name
        go_buildpack   1.10.26   go              go

type:           web
sidecars:       
instances:      3/3
memory usage:   48M
     state     since                  cpu    memory      disk            logging         cpu entitlement   details
#0   running   2025-05-06T20:56:00Z   0.2%   9M of 48M   10.8M of 256M   0B/s of 16K/s   12.3%             
#1   running   2025-05-06T20:55:58Z   0.1%   9M of 48M   10.8M of 256M   0B/s of 16K/s   8.0%              
#2   running   2025-05-06T20:56:00Z   0.1%   9M of 48M   10.8M of 256M   0B/s of 16K/s   9.5%   
```