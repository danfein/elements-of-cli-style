## Restage cf apps

```
cf restage training-app
This action will cause app downtime.

Restaging app training-app in org student-pqvsjp / space default as student-pqvsjp...

Staging app and tracing logs...
   Downloading go_buildpack...
   Downloaded go_buildpack
   Cell bb5049a2-a25d-49bf-accd-51eba9084290 creating container for instance ea2732cb-e94b-4d7d-a77f-fbc839222067
   Security group rules were updated
   Cell bb5049a2-a25d-49bf-accd-51eba9084290 successfully created container for instance ea2732cb-e94b-4d7d-a77f-fbc839222067
   Downloading app package...
   Downloading build artifacts cache...
   Downloaded app package (77.3K)
   Downloaded build artifacts cache (16.7M)
   -----> Go Buildpack version 1.10.26
   -----> Installing godep 80
   Copy [/tmp/buildpacks/c75d16dfd801136a/dependencies/f751943cde454632f4d74e7d14cd8ab8/godep_80_linux_x64_cflinuxfs4_20fea317.tgz]
   -----> Installing glide 0.13.3
   Copy [/tmp/buildpacks/c75d16dfd801136a/dependencies/590428fa6fd00491cda6fe504fd0b519/glide_0.13.3_linux_x64_cflinuxfs4_be64c2ea.tgz]
   -----> Installing dep 0.5.4
   Copy [/tmp/buildpacks/c75d16dfd801136a/dependencies/f98e26ffbd1efd98fdff8d9466933ab3/dep_0.5.4_linux_x64_cflinuxfs4_a4d7f7ea.tgz]
   -----> Installing go 1.22.10
   Copy [/tmp/buildpacks/c75d16dfd801136a/dependencies/186c66a57f9dfe25fb2b102c426ebeb4/go_1.22.10_linux_x64_cflinuxfs4_fb0b56c6.tgz]
   **WARNING** Installing package '.' (default)
   -----> Running: go install -tags cloudfoundry -buildmode pie .
   go: downloading github.com/cloudfoundry-community/go-cfenv v1.18.0
   go: downloading github.com/mitchellh/mapstructure v1.1.2
   Exit status 0
   Uploading droplet, build artifacts cache...
   Uploading droplet...
   Uploading build artifacts cache...
   Uploaded build artifacts cache (16.9M)
   Uploaded droplet (5.7M)
   Uploading complete
   Cell bb5049a2-a25d-49bf-accd-51eba9084290 stopping instance ea2732cb-e94b-4d7d-a77f-fbc839222067
   Cell bb5049a2-a25d-49bf-accd-51eba9084290 destroying container for instance ea2732cb-e94b-4d7d-a77f-fbc839222067
   Cell bb5049a2-a25d-49bf-accd-51eba9084290 successfully destroyed container for instance ea2732cb-e94b-4d7d-a77f-fbc839222067

Restarting app training-app in org student-pqvsjp / space default as student-pqvsjp...

Stopping app...

Waiting for app to start...

Instances starting...
Instances starting...
Instances starting...

name:              training-app
requested state:   started
routes:            
last uploaded:     Tue 06 May 22:19:56 UTC 2025
stack:             cflinuxfs4
buildpacks:        
        name           version   detect output   buildpack name
        go_buildpack   1.10.26   go              go

type:           web
sidecars:       
instances:      3/3
memory usage:   48M
     state     since                  cpu    memory        disk            logging         cpu entitlement   details
#0   running   2025-05-06T22:20:09Z   0.1%   9.1M of 48M   10.8M of 256M   0B/s of 16K/s   10.2%             
#1   running   2025-05-06T22:20:08Z   0.1%   9.1M of 48M   10.8M of 256M   0B/s of 16K/s   11.0%             
#2   running   2025-05-06T22:20:09Z   0.1%   9.5M of 48M   10.8M of 256M   0B/s of 16K/s   10.2%  
```